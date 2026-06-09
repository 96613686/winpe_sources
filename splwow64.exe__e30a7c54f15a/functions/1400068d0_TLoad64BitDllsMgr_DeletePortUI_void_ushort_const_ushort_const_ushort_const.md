# TLoad64BitDllsMgr::DeletePortUI(void *,ushort const *,ushort const *,ushort const *)

- ea: `0x1400068d0`
- end: `0x1400069b0`
- name: `?DeletePortUI@TLoad64BitDllsMgr@@KAKPEAXPEBG11@Z`
- size: `224`
- prototype: `unsigned int __fastcall(void *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting`

## callees

- `0x140006894`
- `0x1400068d0`
- `0x140007298`
- `0x140007548`
- `0x140007d54`
- `0x140016010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140006949`
- `KERNEL32!GetLastError` at `0x140006977`
- `KERNEL32!GetLastError` at `0x140006949`
- `KERNEL32!GetLastError` at `0x140006977`

## pseudocode

```c
__int64 __fastcall TLoad64BitDllsMgr::DeletePortUI(
        void *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  DWORD LastError; // ebx
  TLoad64BitDllsMgr *v8; // rcx
  int v10; // [rsp+40h] [rbp-30h] BYREF
  unsigned int (__fastcall *v11)(const unsigned __int16 *, void *, const unsigned __int16 *); // [rsp+48h] [rbp-28h] BYREF
  unsigned __int64 v12; // [rsp+50h] [rbp-20h] BYREF
  void *v13; // [rsp+58h] [rbp-18h] BYREF
  void *v14[2]; // [rsp+60h] [rbp-10h] BYREF

  v14[0] = 0;
  v13 = 0;
  v12 = 0;
  v10 = 0;
  v11 = 0;
  if ( (unsigned int)TLoad64BitDllsMgr::LoadMonitorUIDll(
                       (__int64)v14,
                       a3,
                       1,
                       &v11,
                       (HMODULE *)v14,
                       (__int64 *)&v13,
                       &v12,
                       &v10) )
  {
    return GetLastError();
  }
  else
  {
    LastError = 0;
    TLoad64BitDllsMgr::IncUIRefCnt(pGLdrObj);
    if ( !v11(a2, a1, a4) )
      LastError = GetLastError();
    TLoad64BitDllsMgr::DecUIRefCnt(pGLdrObj);
    TLoad64BitDllsMgr::ReleaseMonitorActivationContext(v8, v14[0], v13, v12, v10);
  }
  return LastError;
}

```

## disassembly

```asm
0x1400068d0  mov     r11, rsp
0x1400068d3  push    rbp
0x1400068d4  push    rbx
0x1400068d5  push    rsi
0x1400068d6  push    rdi
0x1400068d7  push    r14
0x1400068d9  mov     rbp, rsp
0x1400068dc  sub     rsp, 70h
0x1400068e0  mov     r14, rcx
0x1400068e3  mov     [rbp+var_10], 0
0x1400068eb  mov     rax, r8
0x1400068ee  mov     [rbp+var_18], 0
0x1400068f6  lea     rcx, [rbp+var_30]
0x1400068fa  mov     [rbp+var_20], 0
0x140006902  mov     [r11-60h], rcx
0x140006906  mov     rdi, r9
0x140006909  lea     rcx, [rbp+var_20]
0x14000690d  mov     [rbp+var_30], 0
0x140006914  mov     [r11-68h], rcx
0x140006918  lea     r9, [rbp+var_28]
0x14000691c  lea     rcx, [rbp+var_18]
0x140006920  mov     [rbp+var_28], 0
0x140006928  mov     [r11-70h], rcx
0x14000692c  mov     rsi, rdx
0x14000692f  lea     rcx, [rbp+var_10]
0x140006933  mov     r8d, 1
0x140006939  mov     rdx, rax
0x14000693c  mov     [r11-78h], rcx
0x140006940  call    ?LoadMonitorUIDll@TLoad64BitDllsMgr@@IEBAKPEBGW4EPortOp@@PEAPEAX22PEA_KPEAH@Z; TLoad64BitDllsMgr::LoadMonitorUIDll(ushort const *,EPortOp,void * *,void * *,void * *,unsigned __int64 *,int *)
0x140006945  test    eax, eax
0x140006947  jz      short loc_140006953
0x140006949  call    cs:__imp_GetLastError
0x14000694f  mov     ebx, eax
0x140006951  jmp     short loc_1400069A3
0x140006953  mov     rcx, cs:?pGLdrObj@@3PEAVTLoad64BitDllsMgr@@EA; this
0x14000695a  xor     ebx, ebx
0x14000695c  call    ?IncUIRefCnt@TLoad64BitDllsMgr@@QEAAXXZ; TLoad64BitDllsMgr::IncUIRefCnt(void)
0x140006961  mov     rax, [rbp+var_28]
0x140006965  mov     r8, rdi
0x140006968  mov     rdx, r14
0x14000696b  mov     rcx, rsi
0x14000696e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006973  test    eax, eax
0x140006975  jnz     short loc_14000697F
0x140006977  call    cs:__imp_GetLastError
0x14000697d  mov     ebx, eax
0x14000697f  mov     rcx, cs:?pGLdrObj@@3PEAVTLoad64BitDllsMgr@@EA; this
0x140006986  call    ?DecUIRefCnt@TLoad64BitDllsMgr@@QEAAXXZ; TLoad64BitDllsMgr::DecUIRefCnt(void)
0x14000698b  mov     eax, [rbp+var_30]
0x14000698e  mov     r9, [rbp+var_20]; unsigned __int64
0x140006992  mov     r8, [rbp+var_18]; void *
0x140006996  mov     rdx, [rbp+var_10]; void *
0x14000699a  mov     [rsp+70h+var_50], eax; int
0x14000699e  call    ?ReleaseMonitorActivationContext@TLoad64BitDllsMgr@@IEBAXPEAX0_KH@Z; TLoad64BitDllsMgr::ReleaseMonitorActivationContext(void *,void *,unsigned __int64,int)
0x1400069a3  mov     eax, ebx
0x1400069a5  add     rsp, 70h
0x1400069a9  pop     r14
0x1400069ab  pop     rdi
0x1400069ac  pop     rsi
0x1400069ad  pop     rbx
0x1400069ae  pop     rbp
0x1400069af  retn
```
