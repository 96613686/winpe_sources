# TLoad64BitDllsMgr::AddPortUI(void *,ushort const *,ushort const *,ushort const *)

- ea: `0x1400066c0`
- end: `0x1400067a3`
- name: `?AddPortUI@TLoad64BitDllsMgr@@KAKPEAXPEBG11@Z`
- size: `227`
- prototype: `unsigned int __fastcall(void *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting`

## callees

- `0x1400066c0`
- `0x140006894`
- `0x140007298`
- `0x140007548`
- `0x140007d54`
- `0x140016010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140006739`
- `KERNEL32!GetLastError` at `0x14000676a`
- `KERNEL32!GetLastError` at `0x140006739`
- `KERNEL32!GetLastError` at `0x14000676a`

## pseudocode

```c
__int64 __fastcall TLoad64BitDllsMgr::AddPortUI(
        void *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  DWORD LastError; // ebx
  TLoad64BitDllsMgr *v8; // rcx
  int v10; // [rsp+40h] [rbp-30h] BYREF
  unsigned int (__fastcall *v11)(const unsigned __int16 *, void *, const unsigned __int16 *, _QWORD); // [rsp+48h] [rbp-28h] BYREF
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
                       2,
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
    if ( !v11(a2, a1, a4, 0) )
      LastError = GetLastError();
    TLoad64BitDllsMgr::DecUIRefCnt(pGLdrObj);
    TLoad64BitDllsMgr::ReleaseMonitorActivationContext(v8, v14[0], v13, v12, v10);
  }
  return LastError;
}

```

## disassembly

```asm
0x1400066c0  mov     r11, rsp
0x1400066c3  push    rbp
0x1400066c4  push    rbx
0x1400066c5  push    rsi
0x1400066c6  push    rdi
0x1400066c7  push    r14
0x1400066c9  mov     rbp, rsp
0x1400066cc  sub     rsp, 70h
0x1400066d0  mov     r14, rcx
0x1400066d3  mov     [rbp+var_10], 0
0x1400066db  mov     rax, r8
0x1400066de  mov     [rbp+var_18], 0
0x1400066e6  lea     rcx, [rbp+var_30]
0x1400066ea  mov     [rbp+var_20], 0
0x1400066f2  mov     [r11-60h], rcx
0x1400066f6  mov     rdi, r9
0x1400066f9  lea     rcx, [rbp+var_20]
0x1400066fd  mov     [rbp+var_30], 0
0x140006704  mov     [r11-68h], rcx
0x140006708  lea     r9, [rbp+var_28]
0x14000670c  lea     rcx, [rbp+var_18]
0x140006710  mov     [rbp+var_28], 0
0x140006718  mov     [r11-70h], rcx
0x14000671c  mov     rsi, rdx
0x14000671f  lea     rcx, [rbp+var_10]
0x140006723  mov     r8d, 2
0x140006729  mov     rdx, rax
0x14000672c  mov     [r11-78h], rcx
0x140006730  call    ?LoadMonitorUIDll@TLoad64BitDllsMgr@@IEBAKPEBGW4EPortOp@@PEAPEAX22PEA_KPEAH@Z; TLoad64BitDllsMgr::LoadMonitorUIDll(ushort const *,EPortOp,void * *,void * *,void * *,unsigned __int64 *,int *)
0x140006735  test    eax, eax
0x140006737  jz      short loc_140006743
0x140006739  call    cs:__imp_GetLastError
0x14000673f  mov     ebx, eax
0x140006741  jmp     short loc_140006796
0x140006743  mov     rcx, cs:?pGLdrObj@@3PEAVTLoad64BitDllsMgr@@EA; this
0x14000674a  xor     ebx, ebx
0x14000674c  call    ?IncUIRefCnt@TLoad64BitDllsMgr@@QEAAXXZ; TLoad64BitDllsMgr::IncUIRefCnt(void)
0x140006751  mov     rax, [rbp+var_28]
0x140006755  xor     r9d, r9d
0x140006758  mov     r8, rdi
0x14000675b  mov     rdx, r14
0x14000675e  mov     rcx, rsi
0x140006761  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006766  test    eax, eax
0x140006768  jnz     short loc_140006772
0x14000676a  call    cs:__imp_GetLastError
0x140006770  mov     ebx, eax
0x140006772  mov     rcx, cs:?pGLdrObj@@3PEAVTLoad64BitDllsMgr@@EA; this
0x140006779  call    ?DecUIRefCnt@TLoad64BitDllsMgr@@QEAAXXZ; TLoad64BitDllsMgr::DecUIRefCnt(void)
0x14000677e  mov     eax, [rbp+var_30]
0x140006781  mov     r9, [rbp+var_20]; unsigned __int64
0x140006785  mov     r8, [rbp+var_18]; void *
0x140006789  mov     rdx, [rbp+var_10]; void *
0x14000678d  mov     [rsp+70h+var_50], eax; int
0x140006791  call    ?ReleaseMonitorActivationContext@TLoad64BitDllsMgr@@IEBAXPEAX0_KH@Z; TLoad64BitDllsMgr::ReleaseMonitorActivationContext(void *,void *,unsigned __int64,int)
0x140006796  mov     eax, ebx
0x140006798  add     rsp, 70h
0x14000679c  pop     r14
0x14000679e  pop     rdi
0x14000679f  pop     rsi
0x1400067a0  pop     rbx
0x1400067a1  pop     rbp
0x1400067a2  retn
```
