# CWSHRemote::Invoke(long,_GUID const &,ulong,ushort,tagDISPPARAMS *,tagVARIANT *,tagEXCEPINFO *,uint *)

- ea: `0x140002950`
- end: `0x1400029db`
- name: `?Invoke@CWSHRemote@@UEAAJJAEBU_GUID@@KGPEAUtagDISPPARAMS@@PEAUtagVARIANT@@PEAUtagEXCEPINFO@@PEAI@Z`
- size: `139`
- prototype: `__int64 __fastcall(CWSHRemote *__hidden this, int, const struct _GUID *, unsigned int, unsigned __int16, struct tagDISPPARAMS *, struct tagVARIANT *, struct tagEXCEPINFO *, unsigned int *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x140002950`
- `0x140018010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x140002967`
- `KERNEL32!GetCurrentThreadId` at `0x140002967`

## pseudocode

```c
__int64 __fastcall CWSHRemote::Invoke(
        CWSHRemote *this,
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

  v9 = *((_DWORD *)this + 10);
  if ( GetCurrentThreadId() == v9 )
    return (*(__int64 (__fastcall **)(_QWORD, CWSHRemote *, _QWORD, _QWORD, struct tagDISPPARAMS *, struct tagVARIANT *, struct tagEXCEPINFO *, unsigned int *))(**((_QWORD **)this + 9) + 88LL))(
             *((_QWORD *)this + 9),
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
0x140002950  mov     [rsp+arg_0], rbx
0x140002955  mov     [rsp+arg_8], rsi
0x14000295a  push    rdi
0x14000295b  sub     rsp, 50h
0x14000295f  mov     ebx, [rcx+28h]
0x140002962  mov     esi, edx
0x140002964  mov     rdi, rcx
0x140002967  call    cs:__imp_GetCurrentThreadId
0x14000296d  cmp     eax, ebx
0x14000296f  jz      short loc_140002978
0x140002971  mov     eax, 8000FFFFh
0x140002976  jmp     short loc_1400029CB
0x140002978  mov     rdx, [rsp+58h+arg_40]
0x140002980  mov     r8d, esi
0x140002983  mov     rcx, [rdi+48h]
0x140002987  movzx   r9d, [rsp+58h+arg_20]
0x140002990  mov     [rsp+58h+var_20], rdx
0x140002995  mov     rdx, [rsp+58h+arg_38]
0x14000299d  mov     rax, [rcx]
0x1400029a0  mov     [rsp+58h+var_28], rdx
0x1400029a5  mov     rdx, [rsp+58h+arg_30]
0x1400029ad  mov     [rsp+58h+var_30], rdx
0x1400029b2  mov     rdx, [rsp+58h+arg_28]
0x1400029ba  mov     rax, [rax+58h]
0x1400029be  mov     [rsp+58h+var_38], rdx
0x1400029c3  mov     rdx, rdi
0x1400029c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400029cb  mov     rbx, [rsp+58h+arg_0]
0x1400029d0  mov     rsi, [rsp+58h+arg_8]
0x1400029d5  add     rsp, 50h
0x1400029d9  pop     rdi
0x1400029da  retn
```
