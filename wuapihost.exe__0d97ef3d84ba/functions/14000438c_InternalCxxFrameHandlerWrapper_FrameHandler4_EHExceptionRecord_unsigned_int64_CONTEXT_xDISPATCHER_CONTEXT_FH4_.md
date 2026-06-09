# __InternalCxxFrameHandlerWrapper<__FrameHandler4>(EHExceptionRecord *,unsigned __int64 *,_CONTEXT *,_xDISPATCHER_CONTEXT *,FH4::FuncInfo4 *,int,unsigned __int64 *,uchar)

- ea: `0x14000438c`
- end: `0x1400043d7`
- name: `??$__InternalCxxFrameHandlerWrapper@V__FrameHandler4@@@@YA?AW4_EXCEPTION_DISPOSITION@@PEAUEHExceptionRecord@@PEA_KPEAU_CONTEXT@@PEAU_xDISPATCHER_CONTEXT@@PEAUFuncInfo4@FH4@@H1E@Z`
- size: `75`
- prototype: `__int64 __fastcall(int, int, int, int, struct FH4::FuncInfo4 *, int, __int64, char)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x140002348`
- `0x140002af0`

## callees

- `0x140003008`
- `0x1400040e0`

## pseudocode

```c
__int64 __fastcall __InternalCxxFrameHandlerWrapper<__FrameHandler4>(
        struct EHExceptionRecord *a1,
        unsigned __int64 *a2,
        __int64 a3,
        struct _xDISPATCHER_CONTEXT *a4,
        struct FH4::FuncInfo4 *a5,
        int a6,
        __int64 a7,
        char a8)
{
  unsigned int v8; // ebx

  v8 = __InternalCxxFrameHandler<__FrameHandler4>(a1, a2, a3, a4, a5, a6, a7, a8);
  *(_DWORD *)(_vcrt_getptd() + 120) = -2;
  return v8;
}

```

## disassembly

```asm
0x14000438c  push    rbx
0x14000438e  sub     rsp, 40h
0x140004392  mov     al, [rsp+48h+arg_38]
0x140004399  mov     [rsp+48h+var_10], al; char
0x14000439d  mov     rax, [rsp+48h+arg_30]
0x1400043a5  mov     [rsp+48h+var_18], rax; __int64
0x1400043aa  mov     eax, [rsp+48h+arg_28]
0x1400043ae  mov     [rsp+48h+var_20], eax; int
0x1400043b2  mov     rax, [rsp+48h+arg_20]
0x1400043b7  mov     [rsp+48h+var_28], rax; struct FH4::FuncInfo4 *
0x1400043bc  call    ??$__InternalCxxFrameHandler@V__FrameHandler4@@@@YA?AW4_EXCEPTION_DISPOSITION@@PEAUEHExceptionRecord@@PEA_KPEAU_CONTEXT@@PEAU_xDISPATCHER_CONTEXT@@PEAUFuncInfo4@FH4@@H1E@Z; __InternalCxxFrameHandler<__FrameHandler4>(EHExceptionRecord *,unsigned __int64 *,_CONTEXT *,_xDISPATCHER_CONTEXT *,FH4::FuncInfo4 *,int,unsigned __int64 *,uchar)
0x1400043c1  mov     ebx, eax
0x1400043c3  call    __vcrt_getptd
0x1400043c8  mov     dword ptr [rax+78h], 0FFFFFFFEh
0x1400043cf  mov     eax, ebx
0x1400043d1  add     rsp, 40h
0x1400043d5  pop     rbx
0x1400043d6  retn
0x14000663a  push    rbp
0x14000663c  sub     rsp, 40h
0x140006640  mov     rbp, rdx
0x140006643  call    __vcrt_getptd
0x140006648  mov     dword ptr [rax+78h], 0FFFFFFFEh
0x14000664f  add     rsp, 40h
0x140006653  pop     rbp
0x140006654  retn
```
