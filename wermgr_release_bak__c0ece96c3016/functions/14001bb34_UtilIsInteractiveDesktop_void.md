# UtilIsInteractiveDesktop(void)

- ea: `0x14001bb34`
- end: `0x14001be67`
- name: `?UtilIsInteractiveDesktop@@YAHXZ`
- size: `819`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x14001b9dc`
- `0x14001be70`

## callees

- `0x140003224`
- `0x140003734`
- `0x1400046cc`
- `0x14000e318`
- `0x14000e340`
- `0x14001bb34`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14001be25`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14001be39`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14001be25`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14001be39`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14001bb80`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14001bb80`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001bbc5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001bbf3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001bccb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001bd18`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001bd43`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001bdf4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001bbc5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001bbf3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001bccb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001bd18`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001bd43`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001bdf4`
- `ext-ms-win-ntuser-windowstation-l1-1-0!GetThreadDesktop` at `0x14001bb88`
- `ext-ms-win-ntuser-windowstation-l1-1-0!GetThreadDesktop` at `0x14001bb88`
- `ext-ms-win-ntuser-windowstation-l1-1-0!GetProcessWindowStation` at `0x14001bb77`
- `ext-ms-win-ntuser-windowstation-l1-1-0!GetProcessWindowStation` at `0x14001bb77`
- `ext-ms-win-ntuser-windowstation-l1-1-0!GetUserObjectInformationW` at `0x14001bbbb`
- `ext-ms-win-ntuser-windowstation-l1-1-0!GetUserObjectInformationW` at `0x14001bca1`
- `ext-ms-win-ntuser-windowstation-l1-1-0!GetUserObjectInformationW` at `0x14001bd0e`
- `ext-ms-win-ntuser-windowstation-l1-1-0!GetUserObjectInformationW` at `0x14001bdd2`
- `ext-ms-win-ntuser-windowstation-l1-1-0!GetUserObjectInformationW` at `0x14001bbbb`
- `ext-ms-win-ntuser-windowstation-l1-1-0!GetUserObjectInformationW` at `0x14001bca1`
- `ext-ms-win-ntuser-windowstation-l1-1-0!GetUserObjectInformationW` at `0x14001bd0e`
- `ext-ms-win-ntuser-windowstation-l1-1-0!GetUserObjectInformationW` at `0x14001bdd2`

## pseudocode

```c
__int64 UtilIsInteractiveDesktop(void)
{
  unsigned int v0; // esi
  HWINSTA ProcessWindowStation; // rdi
  DWORD CurrentThreadId; // eax
  HDESK ThreadDesktop; // rax
  HDESK v4; // r15
  DWORD LastError; // eax
  void **unique_for; // rax
  const struct std::nothrow_t *v7; // rdx
  void *v8; // r14
  const struct std::nothrow_t *v9; // rdx
  DWORD v10; // eax
  __int64 v11; // rdx
  void **v12; // rax
  void *v13; // rdi
  const struct std::nothrow_t *v14; // rdx
  DWORD v15; // eax
  DWORD nLengthNeeded; // [rsp+60h] [rbp+30h] BYREF
  void *v18; // [rsp+68h] [rbp+38h] BYREF

  nLengthNeeded = 0;
  v0 = 0;
  if ( !(unsigned __int8)IsGetThreadDesktopPresent() )
    return v0;
  if ( !(unsigned __int8)IsGetThreadDesktopPresent() )
    return v0;
  if ( !(unsigned __int8)IsGetThreadDesktopPresent() )
    return v0;
  ProcessWindowStation = GetProcessWindowStation();
  CurrentThreadId = GetCurrentThreadId();
  ThreadDesktop = GetThreadDesktop(CurrentThreadId);
  v4 = ThreadDesktop;
  if ( !ProcessWindowStation || !ThreadDesktop )
    return v0;
  nLengthNeeded = 0;
  if ( !GetUserObjectInformationW(ProcessWindowStation, 2, 0, 0, &nLengthNeeded) && GetLastError() != 122 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      LastError = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_6bd4eed010b8306f92cf4eba78e3d712_Traceguids, LastError);
    }
    return v0;
  }
  if ( nLengthNeeded == -1 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_6bd4eed010b8306f92cf4eba78e3d712_Traceguids);
    return v0;
  }
  unique_for = (void **)utl::make_unique_for_overwrite<wchar_t [0],0>(&v18, nLengthNeeded + 1);
  v8 = *unique_for;
  *unique_for = 0;
  if ( v18 )
    operator delete(v18, v7);
  if ( v8 )
  {
    if ( GetUserObjectInformationW(ProcessWindowStation, 2, v8, nLengthNeeded, &nLengthNeeded) )
    {
      nLengthNeeded = 0;
      if ( GetUserObjectInformationW(v4, 2, 0, 0, &nLengthNeeded) || GetLastError() == 122 )
      {
        if ( nLengthNeeded )
        {
          v12 = (void **)utl::make_unique_for_overwrite<wchar_t [0],0>(&v18, nLengthNeeded + 1);
          v13 = *v12;
          *v12 = 0;
          if ( v18 )
            operator delete(v18, v9);
          if ( v13 )
          {
            if ( GetUserObjectInformationW(v4, 2, v13, nLengthNeeded, &nLengthNeeded) )
            {
              if ( !(unsigned int)_o__wcsicmp(v8, L"WinSta0") && !(unsigned int)_o__wcsicmp(v13, L"default") )
                v0 = 1;
            }
            else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                   && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v15 = GetLastError();
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_6bd4eed010b8306f92cf4eba78e3d712_Traceguids, v15);
            }
            operator delete(v13, v14);
          }
        }
        else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
               && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_6bd4eed010b8306f92cf4eba78e3d712_Traceguids);
        }
        goto LABEL_43;
      }
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      {
LABEL_43:
        operator delete(v8, v9);
        return v0;
      }
      v10 = GetLastError();
      v11 = 13;
    }
    else
    {
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_43;
      v10 = GetLastError();
      v11 = 12;
    }
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), v11, WPP_6bd4eed010b8306f92cf4eba78e3d712_Traceguids, v10);
    goto LABEL_43;
  }
  return v0;
}

```

## disassembly

```asm
0x14001bb34  mov     [rsp-28h+arg_10], rbx
0x14001bb39  push    rbp
0x14001bb3a  push    rsi
0x14001bb3b  push    rdi
0x14001bb3c  push    r14
0x14001bb3e  push    r15
0x14001bb40  mov     rbp, rsp
0x14001bb43  sub     rsp, 30h
0x14001bb47  mov     [rbp+nLengthNeeded], 0
0x14001bb4e  xor     esi, esi
0x14001bb50  call    IsGetThreadDesktopPresent
0x14001bb55  test    al, al
0x14001bb57  jz      loc_14001BE54
0x14001bb5d  call    IsGetThreadDesktopPresent
0x14001bb62  test    al, al
0x14001bb64  jz      loc_14001BE54
0x14001bb6a  call    IsGetThreadDesktopPresent
0x14001bb6f  test    al, al
0x14001bb71  jz      loc_14001BE54
0x14001bb77  call    cs:__imp_GetProcessWindowStation
0x14001bb7d  mov     rdi, rax
0x14001bb80  call    cs:__imp_GetCurrentThreadId
0x14001bb86  mov     ecx, eax; dwThreadId
0x14001bb88  call    cs:__imp_GetThreadDesktop
0x14001bb8e  mov     r15, rax
0x14001bb91  test    rdi, rdi
0x14001bb94  jz      loc_14001BE54
0x14001bb9a  test    rax, rax
0x14001bb9d  jz      loc_14001BE54
0x14001bba3  lea     rax, [rbp+nLengthNeeded]
0x14001bba7  mov     [rbp+nLengthNeeded], esi
0x14001bbaa  xor     r9d, r9d; nLength
0x14001bbad  mov     [rsp+30h+lpnLengthNeeded], rax; lpnLengthNeeded
0x14001bbb2  xor     r8d, r8d; pvInfo
0x14001bbb5  lea     edx, [rsi+2]; nIndex
0x14001bbb8  mov     rcx, rdi; hObj
0x14001bbbb  call    cs:__imp_GetUserObjectInformationW
0x14001bbc1  test    eax, eax
0x14001bbc3  jnz     short loc_14001BC1B
0x14001bbc5  call    cs:__imp_GetLastError
0x14001bbcb  cmp     eax, 7Ah ; 'z'
0x14001bbce  jz      short loc_14001BC1B
0x14001bbd0  mov     rcx, cs:WPP_GLOBAL_Control
0x14001bbd7  lea     rax, WPP_GLOBAL_Control
0x14001bbde  cmp     rcx, rax
0x14001bbe1  jz      loc_14001BE54
0x14001bbe7  lea     ebx, [rsi+1]
0x14001bbea  test    [rcx+1Ch], bl
0x14001bbed  jz      loc_14001BE54
0x14001bbf3  call    cs:__imp_GetLastError
0x14001bbf9  mov     rcx, cs:WPP_GLOBAL_Control
0x14001bc00  lea     edx, [rsi+0Ah]
0x14001bc03  mov     r9d, eax
0x14001bc06  lea     r8, WPP_6bd4eed010b8306f92cf4eba78e3d712_Traceguids
0x14001bc0d  mov     rcx, [rcx+10h]
0x14001bc11  call    WPP_SF_d
0x14001bc16  jmp     loc_14001BE54
0x14001bc1b  mov     eax, [rbp+nLengthNeeded]
0x14001bc1e  mov     ebx, 1
0x14001bc23  inc     eax
0x14001bc25  cmp     eax, ebx
0x14001bc27  jnb     short loc_14001BC61
0x14001bc29  mov     rcx, cs:WPP_GLOBAL_Control
0x14001bc30  lea     rax, WPP_GLOBAL_Control
0x14001bc37  cmp     rcx, rax
0x14001bc3a  jz      loc_14001BE54
0x14001bc40  test    [rcx+1Ch], bl
0x14001bc43  jz      loc_14001BE54
0x14001bc49  mov     rcx, [rcx+10h]
0x14001bc4d  lea     edx, [rbx+0Ah]
0x14001bc50  lea     r8, WPP_6bd4eed010b8306f92cf4eba78e3d712_Traceguids
0x14001bc57  call    WPP_SF_
0x14001bc5c  jmp     loc_14001BE54
0x14001bc61  mov     edx, eax
0x14001bc63  lea     rcx, [rbp+arg_8]
0x14001bc67  call    ??$make_unique_for_overwrite@$$BY0A@_W$0A@@utl@@YA?AV?$unique_ptr@$$BY0A@_WU?$default_delete@$$BY0A@_W@utl@@@0@_K@Z; utl::make_unique_for_overwrite<wchar_t [0],0>(unsigned __int64)
0x14001bc6c  mov     r14, [rax]
0x14001bc6f  mov     [rax], rsi
0x14001bc72  mov     rcx, [rbp+arg_8]; void *
0x14001bc76  test    rcx, rcx
0x14001bc79  jz      short loc_14001BC80
0x14001bc7b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14001bc80  test    r14, r14
0x14001bc83  jz      loc_14001BE54
0x14001bc89  mov     r9d, [rbp+nLengthNeeded]; nLength
0x14001bc8d  lea     rax, [rbp+nLengthNeeded]
0x14001bc91  mov     r8, r14; pvInfo
0x14001bc94  mov     [rsp+30h+lpnLengthNeeded], rax; lpnLengthNeeded
0x14001bc99  mov     edx, 2; nIndex
0x14001bc9e  mov     rcx, rdi; hObj
0x14001bca1  call    cs:__imp_GetUserObjectInformationW
0x14001bca7  test    eax, eax
0x14001bca9  jnz     short loc_14001BCF5
0x14001bcab  mov     rcx, cs:WPP_GLOBAL_Control
0x14001bcb2  lea     rax, WPP_GLOBAL_Control
0x14001bcb9  cmp     rcx, rax
0x14001bcbc  jz      loc_14001BE4C
0x14001bcc2  test    [rcx+1Ch], bl
0x14001bcc5  jz      loc_14001BE4C
0x14001bccb  call    cs:__imp_GetLastError
0x14001bcd1  mov     edx, 0Ch
0x14001bcd6  mov     rcx, cs:WPP_GLOBAL_Control
0x14001bcdd  lea     r8, WPP_6bd4eed010b8306f92cf4eba78e3d712_Traceguids
0x14001bce4  mov     r9d, eax
0x14001bce7  mov     rcx, [rcx+10h]
0x14001bceb  call    WPP_SF_d
0x14001bcf0  jmp     loc_14001BE4C
0x14001bcf5  xor     r9d, r9d; nLength
0x14001bcf8  mov     [rbp+nLengthNeeded], esi
0x14001bcfb  lea     rax, [rbp+nLengthNeeded]
0x14001bcff  xor     r8d, r8d; pvInfo
0x14001bd02  mov     rcx, r15; hObj
0x14001bd05  mov     [rsp+30h+lpnLengthNeeded], rax; lpnLengthNeeded
0x14001bd0a  lea     edx, [r9+2]; nIndex
0x14001bd0e  call    cs:__imp_GetUserObjectInformationW
0x14001bd14  test    eax, eax
0x14001bd16  jnz     short loc_14001BD50
0x14001bd18  call    cs:__imp_GetLastError
0x14001bd1e  cmp     eax, 7Ah ; 'z'
0x14001bd21  jz      short loc_14001BD50
0x14001bd23  mov     rcx, cs:WPP_GLOBAL_Control
0x14001bd2a  lea     rax, WPP_GLOBAL_Control
0x14001bd31  cmp     rcx, rax
0x14001bd34  jz      loc_14001BE4C
0x14001bd3a  test    [rcx+1Ch], bl
0x14001bd3d  jz      loc_14001BE4C
0x14001bd43  call    cs:__imp_GetLastError
0x14001bd49  mov     edx, 0Dh
0x14001bd4e  jmp     short loc_14001BCD6
0x14001bd50  mov     eax, [rbp+nLengthNeeded]
0x14001bd53  cmp     eax, ebx
0x14001bd55  jnb     short loc_14001BD91
0x14001bd57  mov     rcx, cs:WPP_GLOBAL_Control
0x14001bd5e  lea     rax, WPP_GLOBAL_Control
0x14001bd65  cmp     rcx, rax
0x14001bd68  jz      loc_14001BE4C
0x14001bd6e  test    [rcx+1Ch], bl
0x14001bd71  jz      loc_14001BE4C
0x14001bd77  mov     rcx, [rcx+10h]
0x14001bd7b  lea     r8, WPP_6bd4eed010b8306f92cf4eba78e3d712_Traceguids
0x14001bd82  mov     edx, 0Eh
0x14001bd87  call    WPP_SF_
0x14001bd8c  jmp     loc_14001BE4C
0x14001bd91  lea     edx, [rax+1]
0x14001bd94  lea     rcx, [rbp+arg_8]
0x14001bd98  call    ??$make_unique_for_overwrite@$$BY0A@_W$0A@@utl@@YA?AV?$unique_ptr@$$BY0A@_WU?$default_delete@$$BY0A@_W@utl@@@0@_K@Z; utl::make_unique_for_overwrite<wchar_t [0],0>(unsigned __int64)
0x14001bd9d  mov     rdi, [rax]
0x14001bda0  mov     [rax], rsi
0x14001bda3  mov     rcx, [rbp+arg_8]; void *
0x14001bda7  test    rcx, rcx
0x14001bdaa  jz      short loc_14001BDB1
0x14001bdac  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14001bdb1  test    rdi, rdi
0x14001bdb4  jz      loc_14001BE4C
0x14001bdba  mov     r9d, [rbp+nLengthNeeded]; nLength
0x14001bdbe  lea     rax, [rbp+nLengthNeeded]
0x14001bdc2  mov     r8, rdi; pvInfo
0x14001bdc5  mov     [rsp+30h+lpnLengthNeeded], rax; lpnLengthNeeded
0x14001bdca  mov     edx, 2; nIndex
0x14001bdcf  mov     rcx, r15; hObj
0x14001bdd2  call    cs:__imp_GetUserObjectInformationW
0x14001bdd8  test    eax, eax
0x14001bdda  jnz     short loc_14001BE1B
0x14001bddc  mov     rcx, cs:WPP_GLOBAL_Control
0x14001bde3  lea     rax, WPP_GLOBAL_Control
0x14001bdea  cmp     rcx, rax
0x14001bded  jz      short loc_14001BE44
0x14001bdef  test    [rcx+1Ch], bl
0x14001bdf2  jz      short loc_14001BE44
0x14001bdf4  call    cs:__imp_GetLastError
0x14001bdfa  mov     rcx, cs:WPP_GLOBAL_Control
0x14001be01  lea     r8, WPP_6bd4eed010b8306f92cf4eba78e3d712_Traceguids
0x14001be08  mov     edx, 0Fh
0x14001be0d  mov     r9d, eax
0x14001be10  mov     rcx, [rcx+10h]
0x14001be14  call    WPP_SF_d
0x14001be19  jmp     short loc_14001BE44
0x14001be1b  lea     rdx, aWinsta0; "WinSta0"
0x14001be22  mov     rcx, r14
0x14001be25  call    cs:__imp__o__wcsicmp
0x14001be2b  test    eax, eax
0x14001be2d  jnz     short loc_14001BE44
0x14001be2f  lea     rdx, aDefault; "default"
0x14001be36  mov     rcx, rdi
0x14001be39  call    cs:__imp__o__wcsicmp
0x14001be3f  test    eax, eax
0x14001be41  cmovz   esi, ebx
0x14001be44  mov     rcx, rdi; void *
0x14001be47  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14001be4c  mov     rcx, r14; void *
0x14001be4f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14001be54  mov     rbx, [rsp+30h+arg_10]
0x14001be59  mov     eax, esi
0x14001be5b  add     rsp, 30h
0x14001be5f  pop     r15
0x14001be61  pop     r14
0x14001be63  pop     rdi
0x14001be64  pop     rsi
0x14001be65  pop     rbp
0x14001be66  retn
```
