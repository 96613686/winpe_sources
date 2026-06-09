# CUIDlgBase::UnInitializeDUI(void)

- ea: `0x18000c8d8`
- end: `0x18000c99e`
- name: `?UnInitializeDUI@CUIDlgBase@@IEAAXXZ`
- size: `198`
- prototype: `void __fastcall(CUIDlgBase *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000a42c`
- `0x18000cbc8`

## callees

- `0x180003604`
- `0x18000c8d8`

## import_xrefs

- `KERNEL32!ReleaseActCtx` at `0x18000c97d`
- `KERNEL32!ReleaseActCtx` at `0x18000c97d`
- `KERNEL32!DeactivateActCtx` at `0x18000c973`
- `KERNEL32!DeactivateActCtx` at `0x18000c973`
- `DUI70!UnInitThread` at `0x18000c8f2`
- `DUI70!UnInitThread` at `0x18000c8f2`
- `DUI70!UnInitProcessPriv` at `0x18000c933`
- `DUI70!UnInitProcessPriv` at `0x18000c933`

## pseudocode

```c
void __fastcall CUIDlgBase::UnInitializeDUI(CUIDlgBase *this)
{
  int inited; // eax
  int v3; // eax

  if ( *((_DWORD *)this + 13) )
  {
    inited = UnInitThread();
    if ( inited < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        22,
        WPP_8da448519d113fb3b57e053fb6502830_Traceguids,
        (unsigned int)inited);
  }
  if ( *((_DWORD *)this + 12) )
  {
    v3 = UnInitProcessPriv(&_ImageBase);
    if ( v3 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        23,
        WPP_8da448519d113fb3b57e053fb6502830_Traceguids,
        (unsigned int)v3);
  }
  if ( *((_DWORD *)this + 18) )
  {
    DeactivateActCtx(0, *((_QWORD *)this + 8));
    ReleaseActCtx(*((HANDLE *)this + 7));
    *((_QWORD *)this + 7) = 0;
    *((_QWORD *)this + 8) = 0;
  }
}

```

## disassembly

```asm
0x18000c8d8  mov     [rsp+arg_0], rbx
0x18000c8dd  push    rsi
0x18000c8de  sub     rsp, 20h
0x18000c8e2  cmp     dword ptr [rcx+34h], 0
0x18000c8e6  lea     rsi, WPP_GLOBAL_Control
0x18000c8ed  mov     rbx, rcx
0x18000c8f0  jz      short loc_18000C926
0x18000c8f2  call    cs:__imp_UnInitThread
0x18000c8f8  test    eax, eax
0x18000c8fa  jns     short loc_18000C926
0x18000c8fc  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c903  cmp     rcx, rsi
0x18000c906  jz      short loc_18000C926
0x18000c908  test    byte ptr [rcx+1Ch], 1
0x18000c90c  jz      short loc_18000C926
0x18000c90e  mov     rcx, [rcx+10h]
0x18000c912  lea     r8, WPP_8da448519d113fb3b57e053fb6502830_Traceguids
0x18000c919  mov     edx, 16h
0x18000c91e  mov     r9d, eax
0x18000c921  call    WPP_SF_d
0x18000c926  cmp     dword ptr [rbx+30h], 0
0x18000c92a  jz      short loc_18000C967
0x18000c92c  lea     rcx, __ImageBase
0x18000c933  call    cs:__imp_UnInitProcessPriv
0x18000c939  test    eax, eax
0x18000c93b  jns     short loc_18000C967
0x18000c93d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c944  cmp     rcx, rsi
0x18000c947  jz      short loc_18000C967
0x18000c949  test    byte ptr [rcx+1Ch], 1
0x18000c94d  jz      short loc_18000C967
0x18000c94f  mov     rcx, [rcx+10h]
0x18000c953  lea     r8, WPP_8da448519d113fb3b57e053fb6502830_Traceguids
0x18000c95a  mov     edx, 17h
0x18000c95f  mov     r9d, eax
0x18000c962  call    WPP_SF_d
0x18000c967  cmp     dword ptr [rbx+48h], 0
0x18000c96b  jz      short loc_18000C993
0x18000c96d  mov     rdx, [rbx+40h]; ulCookie
0x18000c971  xor     ecx, ecx; dwFlags
0x18000c973  call    cs:__imp_DeactivateActCtx
0x18000c979  mov     rcx, [rbx+38h]; hActCtx
0x18000c97d  call    cs:__imp_ReleaseActCtx
0x18000c983  mov     qword ptr [rbx+38h], 0
0x18000c98b  mov     qword ptr [rbx+40h], 0
0x18000c993  mov     rbx, [rsp+28h+arg_0]
0x18000c998  add     rsp, 20h
0x18000c99c  pop     rsi
0x18000c99d  retn
```
