# TfsCommitEntry

- ea: `0x18002a7d4`
- end: `0x18002a95d`
- name: `TfsCommitEntry`
- size: `393`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180019240`

## callees

- `0x18000b7b4`
- `0x18000b7dc`
- `0x18002a7d4`
- `0x18002afb0`
- `0x18002cb44`
- `0x18002cfa0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002a873`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002a8cb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002a93a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002a873`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002a8cb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002a93a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002a823`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002a823`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x18002a895`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x18002a895`
- `KERNEL32!SystemTimeToFileTime` at `0x18002a8a4`
- `KERNEL32!SystemTimeToFileTime` at `0x18002a8a4`

## pseudocode

```c
__int64 __fastcall TfsCommitEntry(__int64 a1, __int64 a2, __int64 a3, __int64 a4, __int64 a5)
{
  HLOCAL v5; // rdi
  struct _RTL_CRITICAL_SECTION *v10; // rsi
  unsigned int Entry; // eax
  unsigned int v12; // edi
  __int64 v13; // rdi
  int v14; // r8d
  __int64 v15; // [rsp+30h] [rbp-48h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+38h] [rbp-40h] BYREF

  v5 = DavTfsStore;
  v15 = 0;
  SystemTime = 0;
  if ( !DavTfsStore )
    return 6;
  v10 = (struct _RTL_CRITICAL_SECTION *)((char *)DavTfsStore + 56);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)DavTfsStore + 56));
  Entry = TfsFindEntry(v5, a2, &v15);
  v12 = Entry;
  if ( Entry )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, WPP_5f1a3cf1cc213e2c9d1db611a3b6a3c0_Traceguids, Entry);
    LeaveCriticalSection(v10);
    return v12;
  }
  else
  {
    v13 = v15;
    if ( !v15 || *(_DWORD *)(v15 + 24) )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, WPP_5f1a3cf1cc213e2c9d1db611a3b6a3c0_Traceguids);
      LeaveCriticalSection(v10);
      return 87;
    }
    else
    {
      GetSystemTime(&SystemTime);
      SystemTimeToFileTime(&SystemTime, (LPFILETIME)(v13 + 88));
      *(_QWORD *)(v13 + 80) = a5;
      *(_QWORD *)(v13 + 72) = a4;
      *(_DWORD *)(v13 + 24) = 1;
      *(_DWORD *)(v13 + 20) = 1;
      LeaveCriticalSection(v10);
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_qSS(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, v14, v13, a2, a3);
      return 0;
    }
  }
}

```

## disassembly

```asm
0x18002a7d4  push    rbx
0x18002a7d6  push    rbp
0x18002a7d7  push    rsi
0x18002a7d8  push    rdi
0x18002a7d9  push    r14
0x18002a7db  sub     rsp, 50h
0x18002a7df  mov     rax, cs:__security_cookie
0x18002a7e6  xor     rax, rsp
0x18002a7e9  mov     [rsp+78h+var_30], rax
0x18002a7ee  mov     rdi, cs:DavTfsStore
0x18002a7f5  xorps   xmm0, xmm0
0x18002a7f8  mov     [rsp+78h+var_48], 0
0x18002a801  mov     rbx, r9
0x18002a804  mov     r14, r8
0x18002a807  mov     rbp, rdx
0x18002a80a  movups  xmmword ptr [rsp+78h+SystemTime.wYear], xmm0
0x18002a80f  test    rdi, rdi
0x18002a812  jnz     short loc_18002A81C
0x18002a814  lea     eax, [rdi+6]
0x18002a817  jmp     loc_18002A945
0x18002a81c  lea     rsi, [rdi+38h]
0x18002a820  mov     rcx, rsi; lpCriticalSection
0x18002a823  call    cs:__imp_EnterCriticalSection
0x18002a829  lea     r8, [rsp+78h+var_48]
0x18002a82e  mov     rdx, rbp
0x18002a831  mov     rcx, rdi
0x18002a834  call    TfsFindEntry
0x18002a839  mov     edi, eax
0x18002a83b  test    eax, eax
0x18002a83d  jz      short loc_18002A880
0x18002a83f  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a846  lea     rdx, WPP_GLOBAL_Control
0x18002a84d  cmp     rcx, rdx
0x18002a850  jz      short loc_18002A870
0x18002a852  test    byte ptr [rcx+1Ch], 1
0x18002a856  jz      short loc_18002A870
0x18002a858  mov     rcx, [rcx+10h]
0x18002a85c  lea     r8, WPP_5f1a3cf1cc213e2c9d1db611a3b6a3c0_Traceguids
0x18002a863  mov     edx, 28h ; '('
0x18002a868  mov     r9d, eax
0x18002a86b  call    WPP_SF_d
0x18002a870  mov     rcx, rsi; lpCriticalSection
0x18002a873  call    cs:__imp_LeaveCriticalSection
0x18002a879  mov     eax, edi
0x18002a87b  jmp     loc_18002A945
0x18002a880  mov     rdi, [rsp+78h+var_48]
0x18002a885  test    rdi, rdi
0x18002a888  jz      short loc_18002A909
0x18002a88a  cmp     dword ptr [rdi+18h], 0
0x18002a88e  jnz     short loc_18002A909
0x18002a890  lea     rcx, [rsp+78h+SystemTime]; lpSystemTime
0x18002a895  call    cs:__imp_GetSystemTime
0x18002a89b  lea     rdx, [rdi+58h]; lpFileTime
0x18002a89f  lea     rcx, [rsp+78h+SystemTime]; lpSystemTime
0x18002a8a4  call    cs:__imp_SystemTimeToFileTime
0x18002a8aa  mov     rax, [rsp+78h+arg_20]
0x18002a8b2  mov     rcx, rsi; lpCriticalSection
0x18002a8b5  mov     [rdi+50h], rax
0x18002a8b9  mov     [rdi+48h], rbx
0x18002a8bd  mov     dword ptr [rdi+18h], 1
0x18002a8c4  mov     dword ptr [rdi+14h], 1
0x18002a8cb  call    cs:__imp_LeaveCriticalSection
0x18002a8d1  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a8d8  lea     rdx, WPP_GLOBAL_Control
0x18002a8df  cmp     rcx, rdx
0x18002a8e2  jz      short loc_18002A905
0x18002a8e4  test    byte ptr [rcx+1Ch], 2
0x18002a8e8  jz      short loc_18002A905
0x18002a8ea  mov     rcx, [rcx+10h]
0x18002a8ee  mov     edx, 2Bh ; '+'
0x18002a8f3  mov     [rsp+78h+var_50], r14
0x18002a8f8  mov     r9, rdi
0x18002a8fb  mov     [rsp+78h+var_58], rbp
0x18002a900  call    WPP_SF_qSS
0x18002a905  xor     eax, eax
0x18002a907  jmp     short loc_18002A945
0x18002a909  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a910  lea     rdx, WPP_GLOBAL_Control
0x18002a917  cmp     rcx, rdx
0x18002a91a  jz      short loc_18002A937
0x18002a91c  test    byte ptr [rcx+1Ch], 1
0x18002a920  jz      short loc_18002A937
0x18002a922  mov     rcx, [rcx+10h]
0x18002a926  lea     r8, WPP_5f1a3cf1cc213e2c9d1db611a3b6a3c0_Traceguids
0x18002a92d  mov     edx, 29h ; ')'
0x18002a932  call    WPP_SF_
0x18002a937  mov     rcx, rsi; lpCriticalSection
0x18002a93a  call    cs:__imp_LeaveCriticalSection
0x18002a940  mov     eax, 57h ; 'W'
0x18002a945  mov     rcx, [rsp+78h+var_30]
0x18002a94a  xor     rcx, rsp; StackCookie
0x18002a94d  call    __security_check_cookie
0x18002a952  add     rsp, 50h
0x18002a956  pop     r14
0x18002a958  pop     rdi
0x18002a959  pop     rsi
0x18002a95a  pop     rbp
0x18002a95b  pop     rbx
0x18002a95c  retn
```
