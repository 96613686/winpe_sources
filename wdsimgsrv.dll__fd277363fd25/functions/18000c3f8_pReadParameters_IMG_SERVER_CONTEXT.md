# pReadParameters(_IMG_SERVER_CONTEXT *)

- ea: `0x18000c3f8`
- end: `0x18000c58a`
- name: `?pReadParameters@@YAKPEAU_IMG_SERVER_CONTEXT@@@Z`
- size: `402`
- prototype: `unsigned int __fastcall(struct _IMG_SERVER_CONTEXT *)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180007120`

## callees

- `0x180006d10`
- `0x18000c3f8`
- `0x18000cdc8`
- `0x18000ce90`
- `0x18000cf34`
- `0x180015ff9`
- `0x180016020`

## import_xrefs

- `KERNEL32!HeapFree` at `0x18000c51f`
- `KERNEL32!HeapFree` at `0x18000c544`
- `KERNEL32!HeapFree` at `0x18000c51f`
- `KERNEL32!HeapFree` at `0x18000c544`
- `KERNEL32!GetLastError` at `0x18000c467`
- `KERNEL32!GetLastError` at `0x18000c467`
- `KERNEL32!HeapAlloc` at `0x18000c4c2`
- `KERNEL32!HeapAlloc` at `0x18000c4c2`
- `KERNEL32!GetProcessHeap` at `0x18000c4ab`
- `KERNEL32!GetProcessHeap` at `0x18000c50b`
- `KERNEL32!GetProcessHeap` at `0x18000c530`
- `KERNEL32!GetProcessHeap` at `0x18000c4ab`
- `KERNEL32!GetProcessHeap` at `0x18000c50b`
- `KERNEL32!GetProcessHeap` at `0x18000c530`
- `KERNEL32!GetDynamicTimeZoneInformation` at `0x18000c47d`
- `KERNEL32!GetDynamicTimeZoneInformation` at `0x18000c47d`
- `WdsCommonLib!?WIN32_FROM_HRESULT@@YAKJ@Z` at `0x18000c4f4`
- `WdsCommonLib!?WIN32_FROM_HRESULT@@YAKJ@Z` at `0x18000c4f4`

## pseudocode

```c
__int64 __fastcall pReadParameters(struct _IMG_SERVER_CONTEXT *a1)
{
  unsigned __int16 *v2; // rbx
  unsigned int v3; // edi
  __int64 v4; // rdx
  __int64 v5; // rcx
  __int64 v6; // r8
  BYTE *String; // rax
  BYTE *v8; // rsi
  DWORD LastError; // eax
  __int64 v10; // r14
  unsigned __int64 v11; // r14
  HANDLE ProcessHeap; // rax
  unsigned __int16 *v13; // rax
  int v14; // eax
  HANDLE v15; // rax
  HANDLE v16; // rax
  _TIME_DYNAMIC_ZONE_INFORMATION pTimeZoneInformation; // [rsp+20h] [rbp-1D8h] BYREF

  v2 = 0;
  memset_0(&pTimeZoneInformation, 0, sizeof(pTimeZoneInformation));
  v3 = 0;
  if ( (unsigned int)RegExists() )
    String = RegGetStringEx(v5, v4, v6);
  else
    String = (BYTE *)StrDupe((unsigned __int16 *)&pszSrch);
  v8 = String;
  if ( !String || GetDynamicTimeZoneInformation(&pTimeZoneInformation) == -1 )
  {
    LastError = GetLastError();
  }
  else
  {
    v10 = -1;
    do
      ++v10;
    while ( pTimeZoneInformation.TimeZoneKeyName[v10] );
    v11 = v10 + 1;
    ProcessHeap = GetProcessHeap();
    v13 = (unsigned __int16 *)HeapAlloc(ProcessHeap, 8u, 2 * v11);
    v2 = v13;
    if ( !v13 )
    {
      v3 = 14;
LABEL_17:
      v16 = GetProcessHeap();
      HeapFree(v16, 0, v8);
      return v3;
    }
    v14 = StringCchCopyW(v13, v11, pTimeZoneInformation.TimeZoneKeyName);
    if ( v14 >= 0 )
    {
      *((_QWORD *)a1 + 3) = v8;
      *((_QWORD *)a1 + 2) = v2;
      return v3;
    }
    LastError = WIN32_FROM_HRESULT(v14);
  }
  v3 = LastError;
  if ( LastError )
  {
    if ( v2 )
    {
      v15 = GetProcessHeap();
      HeapFree(v15, 0, v2);
    }
    if ( v8 )
      goto LABEL_17;
  }
  return v3;
}

```

## disassembly

```asm
0x18000c3f8  mov     [rsp+arg_8], rbx
0x18000c3fd  mov     [rsp+arg_10], rbp
0x18000c402  mov     [rsp+arg_18], rsi
0x18000c407  push    rdi
0x18000c408  push    r14
0x18000c40a  push    r15
0x18000c40c  sub     rsp, 1E0h
0x18000c413  mov     rax, cs:__security_cookie
0x18000c41a  xor     rax, rsp
0x18000c41d  mov     [rsp+1F8h+var_28], rax
0x18000c425  mov     rbp, rcx
0x18000c428  xor     r15d, r15d
0x18000c42b  lea     rcx, [rsp+1F8h+pTimeZoneInformation]; void *
0x18000c430  xor     edx, edx; Val
0x18000c432  mov     r8d, 1B0h; Size
0x18000c438  mov     ebx, r15d
0x18000c43b  call    memset_0
0x18000c440  mov     edi, r15d
0x18000c443  call    RegExists
0x18000c448  test    eax, eax
0x18000c44a  jz      short loc_18000C453
0x18000c44c  call    RegGetStringEx
0x18000c451  jmp     short loc_18000C45F
0x18000c453  lea     rcx, pszSrch; unsigned __int16 *
0x18000c45a  call    StrDupe
0x18000c45f  mov     rsi, rax
0x18000c462  test    rax, rax
0x18000c465  jnz     short loc_18000C478
0x18000c467  call    cs:__imp_GetLastError
0x18000c46e  nop     dword ptr [rax+rax+00h]
0x18000c473  jmp     loc_18000C500
0x18000c478  lea     rcx, [rsp+1F8h+pTimeZoneInformation]; pTimeZoneInformation
0x18000c47d  call    cs:__imp_GetDynamicTimeZoneInformation
0x18000c484  nop     dword ptr [rax+rax+00h]
0x18000c489  cmp     eax, 0FFFFFFFFh
0x18000c48c  jz      short loc_18000C467
0x18000c48e  lea     rax, [rsp+1F8h+pTimeZoneInformation.TimeZoneKeyName]
0x18000c496  or      r14, 0FFFFFFFFFFFFFFFFh
0x18000c49a  inc     r14
0x18000c49d  cmp     [rax+r14*2], r15w
0x18000c4a2  jnz     short loc_18000C49A
0x18000c4a4  inc     r14
0x18000c4a7  lea     rbx, [r14+r14]
0x18000c4ab  call    cs:__imp_GetProcessHeap
0x18000c4b2  nop     dword ptr [rax+rax+00h]
0x18000c4b7  mov     r8, rbx; dwBytes
0x18000c4ba  mov     edx, 8; dwFlags
0x18000c4bf  mov     rcx, rax; hHeap
0x18000c4c2  call    cs:__imp_HeapAlloc
0x18000c4c9  nop     dword ptr [rax+rax+00h]
0x18000c4ce  mov     rbx, rax
0x18000c4d1  test    rax, rax
0x18000c4d4  jnz     short loc_18000C4DB
0x18000c4d6  lea     edi, [rax+0Eh]
0x18000c4d9  jmp     short loc_18000C530
0x18000c4db  lea     r8, [rsp+1F8h+pTimeZoneInformation.TimeZoneKeyName]; unsigned __int16 *
0x18000c4e3  mov     rdx, r14; unsigned __int64
0x18000c4e6  mov     rcx, rbx; unsigned __int16 *
0x18000c4e9  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000c4ee  test    eax, eax
0x18000c4f0  jns     short loc_18000C552
0x18000c4f2  mov     ecx, eax
0x18000c4f4  call    cs:__imp_?WIN32_FROM_HRESULT@@YAKJ@Z; WIN32_FROM_HRESULT(long)
0x18000c4fb  nop     dword ptr [rax+rax+00h]
0x18000c500  mov     edi, eax
0x18000c502  test    eax, eax
0x18000c504  jz      short loc_18000C55A
0x18000c506  test    rbx, rbx
0x18000c509  jz      short loc_18000C52B
0x18000c50b  call    cs:__imp_GetProcessHeap
0x18000c512  nop     dword ptr [rax+rax+00h]
0x18000c517  mov     r8, rbx; lpMem
0x18000c51a  xor     edx, edx; dwFlags
0x18000c51c  mov     rcx, rax; hHeap
0x18000c51f  call    cs:__imp_HeapFree
0x18000c526  nop     dword ptr [rax+rax+00h]
0x18000c52b  test    rsi, rsi
0x18000c52e  jz      short loc_18000C55A
0x18000c530  call    cs:__imp_GetProcessHeap
0x18000c537  nop     dword ptr [rax+rax+00h]
0x18000c53c  mov     r8, rsi; lpMem
0x18000c53f  xor     edx, edx; dwFlags
0x18000c541  mov     rcx, rax; hHeap
0x18000c544  call    cs:__imp_HeapFree
0x18000c54b  nop     dword ptr [rax+rax+00h]
0x18000c550  jmp     short loc_18000C55A
0x18000c552  mov     [rbp+18h], rsi
0x18000c556  mov     [rbp+10h], rbx
0x18000c55a  mov     eax, edi
0x18000c55c  mov     rcx, [rsp+1F8h+var_28]
0x18000c564  xor     rcx, rsp; StackCookie
0x18000c567  call    __security_check_cookie
0x18000c56c  lea     r11, [rsp+1F8h+var_18]
0x18000c574  mov     rbx, [r11+28h]
0x18000c578  mov     rbp, [r11+30h]
0x18000c57c  mov     rsi, [r11+38h]
0x18000c580  mov     rsp, r11
0x18000c583  pop     r15
0x18000c585  pop     r14
0x18000c587  pop     rdi
0x18000c588  retn
```
