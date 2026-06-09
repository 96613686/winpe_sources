# Tpm20ResourceMgr::CreateTpm20ResourceMgr(TpmTransport *,bool,Tpm20ResourceMgr * *)

- ea: `0x14001b3d0`
- end: `0x14001b45b`
- name: `?CreateTpm20ResourceMgr@Tpm20ResourceMgr@@SAJPEAVTpmTransport@@_NPEAPEAV1@@Z`
- size: `139`
- prototype: `__int64 __fastcall(struct TpmTransport *, bool, struct Tpm20ResourceMgr **)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x14001483c`

## callees

- `0x140003850`
- `0x140009278`
- `0x14001b2cc`
- `0x14001b3d0`

## pseudocode

```c
__int64 __fastcall Tpm20ResourceMgr::CreateTpm20ResourceMgr(
        struct TpmTransport *a1,
        bool a2,
        struct Tpm20ResourceMgr **a3)
{
  Tpm20ResourceMgr *v6; // rax
  struct Tpm20ResourceMgr *v7; // rax
  unsigned int v8; // ebx

  v6 = (Tpm20ResourceMgr *)AllocatorBase::operator new(0xB8u);
  if ( v6 && (v7 = Tpm20ResourceMgr::Tpm20ResourceMgr(v6, a1, a2)) != 0 )
  {
    v8 = 0;
    *a3 = v7;
  }
  else
  {
    v8 = -1073741670;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_8e0463bd2bbe316f38665ed291c614ef_Traceguids, 3221225626LL);
  }
  return v8;
}

```

## disassembly

```asm
0x14001b3d0  mov     [rsp+arg_0], rbx
0x14001b3d5  mov     [rsp+arg_8], rsi
0x14001b3da  push    rdi
0x14001b3db  sub     rsp, 20h
0x14001b3df  mov     rsi, rcx
0x14001b3e2  mov     rdi, r8
0x14001b3e5  mov     ecx, 0B8h; Size
0x14001b3ea  mov     bl, dl
0x14001b3ec  call    ??2AllocatorBase@@SAPEAX_K@Z; AllocatorBase::operator new(unsigned __int64)
0x14001b3f1  test    rax, rax
0x14001b3f4  jz      short loc_14001B410
0x14001b3f6  mov     r8b, bl; bool
0x14001b3f9  mov     rdx, rsi; struct TpmTransport *
0x14001b3fc  mov     rcx, rax; this
0x14001b3ff  call    ??0Tpm20ResourceMgr@@AEAA@PEAVTpmTransport@@_N@Z; Tpm20ResourceMgr::Tpm20ResourceMgr(TpmTransport *,bool)
0x14001b404  test    rax, rax
0x14001b407  jz      short loc_14001B410
0x14001b409  xor     ebx, ebx
0x14001b40b  mov     [rdi], rax
0x14001b40e  jmp     short loc_14001B448
0x14001b410  mov     ebx, 0C000009Ah
0x14001b415  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14001b41c  lea     rax, WPP_GLOBAL_Control
0x14001b423  cmp     rcx, rax
0x14001b426  jz      short loc_14001B448
0x14001b428  mov     edx, [rcx+2Ch]
0x14001b42b  test    dl, 1
0x14001b42e  jz      short loc_14001B448
0x14001b430  mov     rcx, [rcx+18h]
0x14001b434  lea     r8, WPP_8e0463bd2bbe316f38665ed291c614ef_Traceguids
0x14001b43b  mov     edx, 0Ah
0x14001b440  mov     r9d, ebx
0x14001b443  call    WPP_SF_d
0x14001b448  mov     rsi, [rsp+28h+arg_8]
0x14001b44d  mov     eax, ebx
0x14001b44f  mov     rbx, [rsp+28h+arg_0]
0x14001b454  add     rsp, 20h
0x14001b458  pop     rdi
0x14001b459  retn
```
