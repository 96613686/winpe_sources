# CVaultRpcImpersonate::UnImpersonate(void)

- ea: `0x180015620`
- end: `0x1800156e9`
- name: `?UnImpersonate@CVaultRpcImpersonate@@QEAAXXZ`
- size: `201`
- prototype: `void __fastcall(HANDLE *this)`
- caller_count: `4`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180012ae0`
- `0x180013390`
- `0x1800151d0`
- `0x180015568`

## callees

- `0x180015620`
- `0x18003b7b0`
- `0x18003b7d8`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001567e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001567e`
- `RPCRT4!RpcRevertToSelf` at `0x18001563f`
- `RPCRT4!RpcRevertToSelf` at `0x18001563f`
- `ntdll!NtSetInformationThread` at `0x180015669`
- `ntdll!NtSetInformationThread` at `0x180015669`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CVaultRpcImpersonate::UnImpersonate(HANDLE *this)
{
  NTSTATUS v2; // eax

  if ( this[1] )
  {
    v2 = NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadImpersonationToken, this + 1, 8u);
    if ( v2 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        10,
        WPP_fc1af33029303d26f917cfed6bc21a33_Traceguids,
        (unsigned int)v2);
    CloseHandle(this[1]);
    this[1] = 0;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_fc1af33029303d26f917cfed6bc21a33_Traceguids);
  }
  if ( *(_BYTE *)this )
  {
    RpcRevertToSelf();
    *(_BYTE *)this = 0;
  }
}

```

## disassembly

```asm
0x180015620  push    rbx
0x180015622  sub     rsp, 20h
0x180015626  cmp     qword ptr [rcx+8], 0
0x18001562b  mov     rbx, rcx
0x18001562e  mov     [rsp+28h+arg_8], rdi
0x180015633  jnz     short loc_18001564E
0x180015635  cmp     byte ptr [rbx], 0
0x180015638  mov     rdi, [rsp+28h+arg_8]
0x18001563d  jz      short loc_180015648
0x18001563f  call    cs:__imp_RpcRevertToSelf
0x180015645  mov     byte ptr [rbx], 0
0x180015648  add     rsp, 20h
0x18001564c  pop     rbx
0x18001564d  retn
0x18001564e  lea     r8, [rcx+8]; ThreadInformation
0x180015652  mov     [rsp+28h+arg_0], rsi
0x180015657  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x18001565e  mov     r9d, 8; ThreadInformationLength
0x180015664  mov     edx, 5; ThreadInformationClass
0x180015669  call    cs:__imp_NtSetInformationThread
0x18001566f  lea     rsi, WPP_GLOBAL_Control
0x180015676  test    eax, eax
0x180015678  js      short loc_1800156BD
0x18001567a  mov     rcx, [rbx+8]; hObject
0x18001567e  call    cs:__imp_CloseHandle
0x180015684  mov     qword ptr [rbx+8], 0
0x18001568c  mov     rcx, cs:WPP_GLOBAL_Control
0x180015693  cmp     rcx, rsi
0x180015696  mov     rsi, [rsp+28h+arg_0]
0x18001569b  jz      short loc_180015635
0x18001569d  test    byte ptr [rcx+1Ch], 8
0x1800156a1  jz      short loc_180015635
0x1800156a3  mov     rcx, [rcx+10h]
0x1800156a7  lea     r8, WPP_fc1af33029303d26f917cfed6bc21a33_Traceguids
0x1800156ae  mov     edx, 0Bh
0x1800156b3  call    WPP_SF_
0x1800156b8  jmp     loc_180015635
0x1800156bd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800156c4  cmp     rcx, rsi
0x1800156c7  jz      short loc_18001567A
0x1800156c9  test    byte ptr [rcx+1Ch], 2
0x1800156cd  jz      short loc_18001567A
0x1800156cf  mov     rcx, [rcx+10h]
0x1800156d3  lea     r8, WPP_fc1af33029303d26f917cfed6bc21a33_Traceguids
0x1800156da  mov     edx, 0Ah
0x1800156df  mov     r9d, eax
0x1800156e2  call    WPP_SF_d
0x1800156e7  jmp     short loc_18001567A
```
