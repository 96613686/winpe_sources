# CVaultRpcImpersonate::~CVaultRpcImpersonate(void)

- ea: `0x180015568`
- end: `0x180015619`
- name: `??1CVaultRpcImpersonate@@QEAA@XZ`
- size: `177`
- prototype: `void __fastcall(CVaultRpcImpersonate *__hidden this)`
- caller_count: `19`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180012470`
- `0x180012ae0`
- `0x1800151d0`
- `0x180015e30`
- `0x18001eda0`
- `0x180026a80`
- `0x180029690`
- `0x18002f5e0`
- `0x180034460`
- `0x180045df0`
- `0x180046040`
- `0x180046920`
- `0x180046d90`
- `0x180047610`
- `0x180047890`
- `0x180047e90`
- `0x180048140`
- `0x1800483f0`
- `0x18004c350`

## callees

- `0x180015568`
- `0x180015620`
- `0x18003b7b0`
- `0x18003b7d8`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800155b6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800155b6`
- `ntdll!NtSetInformationThread` at `0x1800155a1`
- `ntdll!NtSetInformationThread` at `0x1800155a1`

## pseudocode

```c
void __fastcall CVaultRpcImpersonate::~CVaultRpcImpersonate(HANDLE *this)
{
  NTSTATUS v2; // eax

  CVaultRpcImpersonate::UnImpersonate(this);
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
}

```

## disassembly

```asm
0x180015568  mov     [rsp+arg_0], rbx
0x18001556d  push    rdi
0x18001556e  sub     rsp, 20h
0x180015572  mov     rbx, rcx
0x180015575  call    ?UnImpersonate@CVaultRpcImpersonate@@QEAAXXZ; CVaultRpcImpersonate::UnImpersonate(void)
0x18001557a  cmp     qword ptr [rbx+8], 0
0x18001557f  jnz     short loc_18001558C
0x180015581  mov     rbx, [rsp+28h+arg_0]
0x180015586  add     rsp, 20h
0x18001558a  pop     rdi
0x18001558b  retn
0x18001558c  mov     r9d, 8; ThreadInformationLength
0x180015592  lea     r8, [rbx+8]; ThreadInformation
0x180015596  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x18001559d  lea     edx, [r9-3]; ThreadInformationClass
0x1800155a1  call    cs:__imp_NtSetInformationThread
0x1800155a7  lea     rdi, WPP_GLOBAL_Control
0x1800155ae  test    eax, eax
0x1800155b0  js      short loc_1800155ED
0x1800155b2  mov     rcx, [rbx+8]; hObject
0x1800155b6  call    cs:__imp_CloseHandle
0x1800155bc  mov     qword ptr [rbx+8], 0
0x1800155c4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800155cb  cmp     rcx, rdi
0x1800155ce  jz      short loc_180015581
0x1800155d0  test    byte ptr [rcx+1Ch], 8
0x1800155d4  jz      short loc_180015581
0x1800155d6  mov     rcx, [rcx+10h]
0x1800155da  lea     r8, WPP_fc1af33029303d26f917cfed6bc21a33_Traceguids
0x1800155e1  mov     edx, 0Bh
0x1800155e6  call    WPP_SF_
0x1800155eb  jmp     short loc_180015581
0x1800155ed  mov     rcx, cs:WPP_GLOBAL_Control
0x1800155f4  cmp     rcx, rdi
0x1800155f7  jz      short loc_1800155B2
0x1800155f9  test    byte ptr [rcx+1Ch], 2
0x1800155fd  jz      short loc_1800155B2
0x1800155ff  mov     rcx, [rcx+10h]
0x180015603  lea     r8, WPP_fc1af33029303d26f917cfed6bc21a33_Traceguids
0x18001560a  mov     edx, 0Ah
0x18001560f  mov     r9d, eax
0x180015612  call    WPP_SF_d
0x180015617  jmp     short loc_1800155B2
```
