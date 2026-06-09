# InitActivationContext(void * *,unsigned __int64 *)

- ea: `0x180004260`
- end: `0x180004385`
- name: `?InitActivationContext@@YAJPEAPEAXPEA_K@Z`
- size: `293`
- prototype: `__int64 __fastcall(void **, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000c268`

## callees

- `0x180003604`
- `0x180003fe4`
- `0x180004260`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800042cc`
- `KERNEL32!GetLastError` at `0x18000430e`
- `KERNEL32!GetLastError` at `0x1800042cc`
- `KERNEL32!GetLastError` at `0x18000430e`
- `KERNEL32!CreateActCtxW` at `0x1800042bd`
- `KERNEL32!CreateActCtxW` at `0x1800042bd`
- `KERNEL32!ActivateActCtx` at `0x180004304`
- `KERNEL32!ActivateActCtx` at `0x180004304`
- `KERNEL32!ReleaseActCtx` at `0x18000435b`
- `KERNEL32!ReleaseActCtx` at `0x18000435b`

## pseudocode

```c
__int64 __fastcall InitActivationContext(void **a1, unsigned __int64 *a2)
{
  HANDLE v4; // rax
  void *v5; // rdi
  DWORD LastError; // eax
  unsigned int v7; // ebx
  _QWORD *v8; // rcx
  __int64 v9; // rdx
  DWORD v10; // eax
  ACTCTXW pActCtx; // [rsp+20h] [rbp-48h] BYREF
  ULONG_PTR Cookie; // [rsp+80h] [rbp+18h] BYREF

  memset(&pActCtx.lpSource, 0, 24);
  pActCtx.lpApplicationName = 0;
  pActCtx.cbSize = 56;
  pActCtx.dwFlags = 136;
  pActCtx.lpResourceName = (LPCWSTR)2;
  Cookie = 0;
  pActCtx.hModule = &_ImageBase;
  v4 = CreateActCtxW(&pActCtx);
  v5 = v4;
  if ( v4 == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    v7 = ERROR_HR_FROM_WIN32(LastError);
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v9 = 23;
LABEL_9:
      WPP_SF_d(v8[2], v9, WPP_da26f2d1156739261f61a97d8df66789_Traceguids, v7);
    }
  }
  else
  {
    if ( ActivateActCtx(v4, &Cookie) )
    {
      *a2 = Cookie;
      v7 = 0;
      *a1 = v5;
      return v7;
    }
    v10 = GetLastError();
    v7 = ERROR_HR_FROM_WIN32(v10);
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v9 = 24;
      goto LABEL_9;
    }
  }
  if ( (v7 & 0x80000000) != 0 && v5 != (void *)-1LL )
    ReleaseActCtx(v5);
  return v7;
}

```

## disassembly

```asm
0x180004260  mov     rax, rsp
0x180004263  mov     [rax+8], rbx
0x180004267  mov     [rax+10h], rsi
0x18000426b  push    rdi
0x18000426c  sub     rsp, 60h
0x180004270  mov     qword ptr [rax-30h], 0
0x180004278  xorps   xmm0, xmm0
0x18000427b  movdqu  xmmword ptr [rax-40h], xmm0
0x180004280  mov     qword ptr [rax-20h], 0
0x180004288  mov     rsi, rcx
0x18000428b  mov     dword ptr [rax-48h], 38h ; '8'
0x180004292  lea     rcx, [rsp+68h+pActCtx]; pActCtx
0x180004297  mov     dword ptr [rax-44h], 88h
0x18000429e  mov     rbx, rdx
0x1800042a1  mov     qword ptr [rax-28h], 2
0x1800042a9  mov     qword ptr [rax+18h], 0
0x1800042b1  lea     rax, __ImageBase
0x1800042b8  mov     [rsp+68h+pActCtx.hModule], rax
0x1800042bd  call    cs:__imp_CreateActCtxW
0x1800042c3  mov     rdi, rax
0x1800042c6  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800042ca  jnz     short loc_1800042F9
0x1800042cc  call    cs:__imp_GetLastError
0x1800042d2  mov     ecx, eax; unsigned int
0x1800042d4  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x1800042d9  mov     ebx, eax
0x1800042db  mov     rcx, cs:WPP_GLOBAL_Control
0x1800042e2  lea     rax, WPP_GLOBAL_Control
0x1800042e9  cmp     rcx, rax
0x1800042ec  jz      short loc_18000434E
0x1800042ee  test    byte ptr [rcx+1Ch], 1
0x1800042f2  jz      short loc_18000434E
0x1800042f4  lea     edx, [rdi+18h]
0x1800042f7  jmp     short loc_18000433B
0x1800042f9  lea     rdx, [rsp+68h+Cookie]; lpCookie
0x180004301  mov     rcx, rdi; hActCtx
0x180004304  call    cs:__imp_ActivateActCtx
0x18000430a  test    eax, eax
0x18000430c  jnz     short loc_180004363
0x18000430e  call    cs:__imp_GetLastError
0x180004314  mov     ecx, eax; unsigned int
0x180004316  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x18000431b  mov     ebx, eax
0x18000431d  mov     rcx, cs:WPP_GLOBAL_Control
0x180004324  lea     rax, WPP_GLOBAL_Control
0x18000432b  cmp     rcx, rax
0x18000432e  jz      short loc_18000434E
0x180004330  test    byte ptr [rcx+1Ch], 1
0x180004334  jz      short loc_18000434E
0x180004336  mov     edx, 18h
0x18000433b  mov     rcx, [rcx+10h]
0x18000433f  lea     r8, WPP_da26f2d1156739261f61a97d8df66789_Traceguids
0x180004346  mov     r9d, ebx
0x180004349  call    WPP_SF_d
0x18000434e  test    ebx, ebx
0x180004350  jns     short loc_180004373
0x180004352  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x180004356  jz      short loc_180004373
0x180004358  mov     rcx, rdi; hActCtx
0x18000435b  call    cs:__imp_ReleaseActCtx
0x180004361  jmp     short loc_180004373
0x180004363  mov     rax, [rsp+68h+Cookie]
0x18000436b  mov     [rbx], rax
0x18000436e  xor     ebx, ebx
0x180004370  mov     [rsi], rdi
0x180004373  mov     rsi, [rsp+68h+arg_8]
0x180004378  mov     eax, ebx
0x18000437a  mov     rbx, [rsp+68h+arg_0]
0x18000437f  add     rsp, 60h
0x180004383  pop     rdi
0x180004384  retn
```
