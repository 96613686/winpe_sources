# CWSHRemote::CError::Invoke(long,_GUID const &,ulong,ushort,tagDISPPARAMS *,tagVARIANT *,tagEXCEPINFO *,uint *)

- ea: `0x1400017d0`
- end: `0x14000185b`
- name: `?Invoke@CError@CWSHRemote@@UEAAJJAEBU_GUID@@KGPEAUtagDISPPARAMS@@PEAUtagVARIANT@@PEAUtagEXCEPINFO@@PEAI@Z`
- size: `139`
- prototype: `__int64 __fastcall(CWSHRemote::CError *__hidden this, int, const struct _GUID *, unsigned int, unsigned __int16, struct tagDISPPARAMS *, struct tagVARIANT *, struct tagEXCEPINFO *, unsigned int *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1400017d0`
- `0x140018010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1400017e7`
- `KERNEL32!GetCurrentThreadId` at `0x1400017e7`

## pseudocode

```c
__int64 __fastcall CWSHRemote::CError::Invoke(
        CWSHRemote::CError *this,
        unsigned int a2,
        const struct _GUID *a3,
        __int64 a4,
        unsigned __int16 a5,
        struct tagDISPPARAMS *a6,
        struct tagVARIANT *a7,
        struct tagEXCEPINFO *a8,
        unsigned int *a9)
{
  int v9; // ebx

  v9 = *((_DWORD *)this + 3);
  if ( GetCurrentThreadId() == v9 )
    return (*(__int64 (__fastcall **)(_QWORD, CWSHRemote::CError *, _QWORD, _QWORD, struct tagDISPPARAMS *, struct tagVARIANT *, struct tagEXCEPINFO *, unsigned int *))(**((_QWORD **)this + 7) + 88LL))(
             *((_QWORD *)this + 7),
             this,
             a2,
             a5,
             a6,
             a7,
             a8,
             a9);
  else
    return 2147549183LL;
}

```

## disassembly

```asm
0x1400017d0  mov     [rsp+arg_0], rbx
0x1400017d5  mov     [rsp+arg_8], rsi
0x1400017da  push    rdi
0x1400017db  sub     rsp, 50h
0x1400017df  mov     ebx, [rcx+0Ch]
0x1400017e2  mov     esi, edx
0x1400017e4  mov     rdi, rcx
0x1400017e7  call    cs:__imp_GetCurrentThreadId
0x1400017ed  cmp     eax, ebx
0x1400017ef  jz      short loc_1400017F8
0x1400017f1  mov     eax, 8000FFFFh
0x1400017f6  jmp     short loc_14000184B
0x1400017f8  mov     rdx, [rsp+58h+arg_40]
0x140001800  mov     r8d, esi
0x140001803  mov     rcx, [rdi+38h]
0x140001807  movzx   r9d, [rsp+58h+arg_20]
0x140001810  mov     [rsp+58h+var_20], rdx
0x140001815  mov     rdx, [rsp+58h+arg_38]
0x14000181d  mov     rax, [rcx]
0x140001820  mov     [rsp+58h+var_28], rdx
0x140001825  mov     rdx, [rsp+58h+arg_30]
0x14000182d  mov     [rsp+58h+var_30], rdx
0x140001832  mov     rdx, [rsp+58h+arg_28]
0x14000183a  mov     rax, [rax+58h]
0x14000183e  mov     [rsp+58h+var_38], rdx
0x140001843  mov     rdx, rdi
0x140001846  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000184b  mov     rbx, [rsp+58h+arg_0]
0x140001850  mov     rsi, [rsp+58h+arg_8]
0x140001855  add     rsp, 50h
0x140001859  pop     rdi
0x14000185a  retn
```
