# Tcp::CleanupSendNotifications(void *,ulong *,ulong *)

- ea: `0x10043a8e0`
- end: `0x10043ab36`
- name: `?CleanupSendNotifications@Tcp@@CA?AW4SOS_TIMERRESULT@@PEAXPEAK1@Z`
- size: `598`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callees

- `0x10042b7f0`
- `0x10042b9b0`
- `0x10042c270`
- `0x10042c430`
- `0x10043a8e0`
- `0x10045d370`
- `0x100486af0`

## import_xrefs

- `KERNEL32!InterlockedPopEntrySList` at `0x10043a977`
- `KERNEL32!InterlockedPopEntrySList` at `0x10043aac5`
- `KERNEL32!InterlockedPopEntrySList` at `0x10043a977`
- `KERNEL32!InterlockedPopEntrySList` at `0x10043aac5`
- `KERNEL32!InitializeSListHead` at `0x10043a95a`
- `KERNEL32!InitializeSListHead` at `0x10043a95a`
- `KERNEL32!InterlockedPushEntrySList` at `0x10043aa7f`
- `KERNEL32!InterlockedPushEntrySList` at `0x10043aada`
- `KERNEL32!InterlockedPushEntrySList` at `0x10043aa7f`
- `KERNEL32!InterlockedPushEntrySList` at `0x10043aada`
- `KERNEL32!WaitForSingleObject` at `0x10043a9a6`
- `KERNEL32!WaitForSingleObject` at `0x10043a9a6`
- `KERNEL32!CloseHandle` at `0x10043a9bf`
- `KERNEL32!CloseHandle` at `0x10043a9bf`
- `KERNEL32!GetLastError` at `0x10043a9c9`
- `KERNEL32!GetLastError` at `0x10043aa21`
- `KERNEL32!GetLastError` at `0x10043a9c9`
- `KERNEL32!GetLastError` at `0x10043aa21`
- `sqldk!??3@YAXPEAX_K@Z` at `0x10043aa05`
- `sqldk!??3@YAXPEAX_K@Z` at `0x10043aa16`
- `sqldk!??3@YAXPEAX_K@Z` at `0x10043aa6c`
- `sqldk!??3@YAXPEAX_K@Z` at `0x10043aa05`
- `sqldk!??3@YAXPEAX_K@Z` at `0x10043aa16`
- `sqldk!??3@YAXPEAX_K@Z` at `0x10043aa6c`

## string_xrefs

- `0x10043a916`: `sql\common\dk\sni\src\tcp.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 Tcp::CleanupSendNotifications()
{
  int v0; // ebp
  int v1; // r15d
  int v2; // r14d
  PSLIST_ENTRY v3; // rax
  struct _SLIST_ENTRY *v4; // rsi
  HANDLE *p_Next; // rbx
  DWORD v6; // eax
  DWORD v7; // eax
  DWORD LastError; // eax
  DWORD v9; // edi
  struct _SLIST_ENTRY *v10; // rax
  const wchar_t *v11; // r9
  unsigned int v12; // ebx
  __int64 v14; // [rsp+20h] [rbp-88h]
  __int64 v15; // [rsp+28h] [rbp-80h]
  union _SLIST_HEADER ListHead; // [rsp+60h] [rbp-48h] BYREF

  if ( (g_XeSniPkg_enabledBitmap & 0x40) != 0 )
    SNIXE_SNI_ENTER_ON("sql\\common\\dk\\sni\\src\\tcp.cpp", "Tcp::CleanupSendNotifications", 7714, L"API|SNI");
  InitializeSListHead(&ListHead);
  v0 = 0;
  v1 = 0;
  v2 = 0;
  while ( 1 )
  {
    v3 = InterlockedPopEntrySList(&Tcp::s_slhNotificationsToClose);
    v4 = v3;
    if ( !v3 )
      break;
    ++v0;
    p_Next = (HANDLE *)&v3[1].Next->Next;
    if ( !p_Next )
      goto LABEL_13;
    if ( *(_DWORD *)p_Next == 259 || (v6 = WaitForSingleObject(p_Next[3], 0), v6 == 258) )
    {
      InterlockedPushEntrySList(&ListHead, v4);
    }
    else if ( v6 )
    {
      LastError = GetLastError();
      v9 = LastError;
      if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
      {
        LODWORD(v14) = LastError;
        SNIXE_SNI_ERROR_ON(
          "sql\\common\\dk\\sni\\src\\tcp.cpp",
          "Tcp::CleanupSendNotifications",
          7764,
          L"ERR|SNIWaiting for auto-tuning overlapped failed: %d{WINERR}, ovl %p{LPWSAOVERLAPPED}\n",
          v14,
          p_Next);
      }
      scierrlog(0x65D9u, v9);
      ++v2;
      operator delete(v4, 0x20u);
    }
    else
    {
      if ( !CloseHandle(p_Next[3]) )
      {
        v7 = GetLastError();
        if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
        {
          LODWORD(v14) = v7;
          SNIXE_SNI_ERROR_ON(
            "sql\\common\\dk\\sni\\src\\tcp.cpp",
            "Tcp::CleanupSendNotifications",
            7751,
            L"ERR|SNIClosing event handle failed: %d{WINERR}, ovl %p{LPWSAOVERLAPPED}\n",
            v14,
            p_Next);
        }
      }
      p_Next[3] = 0;
      operator delete(p_Next, 0x20u);
      ++v1;
LABEL_13:
      operator delete(v4, 0x20u);
    }
  }
  if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
  {
    LODWORD(v15) = v1;
    LODWORD(v14) = v0;
    SNIXE_SNI_TRACE_ON(
      "sql\\common\\dk\\sni\\src\\tcp.cpp",
      "Tcp::CleanupSendNotifications",
      7789,
      L"SNIItems processed: %d, items closed: %d, items failed: %d.\n",
      v14,
      v15,
      v2);
  }
  while ( 1 )
  {
    v10 = InterlockedPopEntrySList(&ListHead);
    if ( !v10 )
      break;
    InterlockedPushEntrySList(&Tcp::s_slhNotificationsToClose, v10);
  }
  v12 = 3;
  if ( v0 )
    v12 = 0;
  if ( (g_XeSniPkg_enabledBitmap & 0x80u) != 0 )
    SNIXE_SNI_LEAVE_ON("sql\\common\\dk\\sni\\src\\tcp.cpp", "Tcp::CleanupSendNotifications", 7714, v11);
  return v12;
}

```

## disassembly

```asm
0x10043a8e0  mov     r11, rsp
0x10043a8e3  push    rdi
0x10043a8e4  push    r12
0x10043a8e6  push    r13
0x10043a8e8  push    r14
0x10043a8ea  push    r15
0x10043a8ec  sub     rsp, 80h
0x10043a8f3  mov     qword ptr [r11-68h], 0FFFFFFFFFFFFFFFEh
0x10043a8fb  mov     [r11+8], rbx
0x10043a8ff  mov     [r11+10h], rbp
0x10043a903  mov     [r11+18h], rsi
0x10043a907  mov     rax, cs:__security_cookie
0x10043a90e  xor     rax, rsp
0x10043a911  mov     [rsp+0A8h+var_38], rax
0x10043a916  lea     r12, aSqlCommonDkSni_3; "sql\\common\\dk\\sni\\src\\tcp.cpp"
0x10043a91d  mov     [r11-60h], r12
0x10043a921  lea     r13, aTcpCleanupsend; "Tcp::CleanupSendNotifications"
0x10043a928  mov     [r11-58h], r13
0x10043a92c  mov     [rsp+0A8h+var_50], 1E22h
0x10043a934  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 40h; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10043a93b  jz      short loc_10043A955
0x10043a93d  lea     r9, aApiSni; "API|SNI"
0x10043a944  mov     r8d, 1E22h; int
0x10043a94a  mov     rdx, r13; char *
0x10043a94d  mov     rcx, r12; char *
0x10043a950  call    ?SNIXE_SNI_ENTER_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ENTER_ON(char const *,char const *,int,wchar_t const *,...)
0x10043a955  lea     rcx, [rsp+0A8h+ListHead]; ListHead
0x10043a95a  call    cs:__imp_InitializeSListHead
0x10043a960  xor     edi, edi
0x10043a962  mov     ebp, edi
0x10043a964  mov     r15d, edi
0x10043a967  mov     r14d, edi
0x10043a96a  nop     word ptr [rax+rax+00h]
0x10043a970  lea     rcx, ?s_slhNotificationsToClose@Tcp@@1T_SLIST_HEADER@@A; ListHead
0x10043a977  call    cs:__imp_InterlockedPopEntrySList
0x10043a97d  mov     rsi, rax
0x10043a980  test    rax, rax
0x10043a983  jz      loc_10043AA8A
0x10043a989  inc     ebp
0x10043a98b  mov     rbx, [rax+10h]
0x10043a98f  test    rbx, rbx
0x10043a992  jz      short loc_10043AA0E
0x10043a994  cmp     dword ptr [rbx], 103h
0x10043a99a  jz      loc_10043AA77
0x10043a9a0  xor     edx, edx; dwMilliseconds
0x10043a9a2  mov     rcx, [rbx+18h]; hHandle
0x10043a9a6  call    cs:__imp_WaitForSingleObject
0x10043a9ac  cmp     eax, 102h
0x10043a9b1  jz      loc_10043AA77
0x10043a9b7  test    eax, eax
0x10043a9b9  jnz     short loc_10043AA21
0x10043a9bb  mov     rcx, [rbx+18h]; hObject
0x10043a9bf  call    cs:__imp_CloseHandle
0x10043a9c5  test    eax, eax
0x10043a9c7  jnz     short loc_10043A9F9
0x10043a9c9  call    cs:__imp_GetLastError
0x10043a9cf  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 2; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10043a9d6  jz      short loc_10043A9F9
0x10043a9d8  mov     [rsp+0A8h+var_80], rbx
0x10043a9dd  mov     dword ptr [rsp+0A8h+var_88], eax
0x10043a9e1  lea     r9, aErrSniclosingE_0; "ERR|SNIClosing event handle failed: %d{"...
0x10043a9e8  mov     r8d, 1E47h; int
0x10043a9ee  mov     rdx, r13; char *
0x10043a9f1  mov     rcx, r12; char *
0x10043a9f4  call    ?SNIXE_SNI_ERROR_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ERROR_ON(char const *,char const *,int,wchar_t const *,...)
0x10043a9f9  mov     [rbx+18h], rdi
0x10043a9fd  mov     edx, 20h ; ' '
0x10043aa02  mov     rcx, rbx
0x10043aa05  call    cs:__imp_??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x10043aa0b  inc     r15d
0x10043aa0e  mov     edx, 20h ; ' '
0x10043aa13  mov     rcx, rsi
0x10043aa16  call    cs:__imp_??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x10043aa1c  jmp     loc_10043A970
0x10043aa21  call    cs:__imp_GetLastError
0x10043aa27  mov     edi, eax
0x10043aa29  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 2; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10043aa30  jz      short loc_10043AA53
0x10043aa32  mov     [rsp+0A8h+var_80], rbx
0x10043aa37  mov     dword ptr [rsp+0A8h+var_88], eax
0x10043aa3b  lea     r9, aErrSniwaitingF; "ERR|SNIWaiting for auto-tuning overlapp"...
0x10043aa42  mov     r8d, 1E54h; int
0x10043aa48  mov     rdx, r13; char *
0x10043aa4b  mov     rcx, r12; char *
0x10043aa4e  call    ?SNIXE_SNI_ERROR_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ERROR_ON(char const *,char const *,int,wchar_t const *,...)
0x10043aa53  mov     edx, edi
0x10043aa55  mov     ecx, 65D9h; unsigned int
0x10043aa5a  call    ?scierrlog@@YAXKZZ; scierrlog(ulong,...)
0x10043aa5f  inc     r14d
0x10043aa62  xor     edi, edi
0x10043aa64  mov     edx, 20h ; ' '
0x10043aa69  mov     rcx, rsi
0x10043aa6c  call    cs:__imp_??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x10043aa72  jmp     loc_10043A970
0x10043aa77  mov     rdx, rsi; ListEntry
0x10043aa7a  lea     rcx, [rsp+0A8h+ListHead]; ListHead
0x10043aa7f  call    cs:__imp_InterlockedPushEntrySList
0x10043aa85  jmp     loc_10043A970
0x10043aa8a  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 1; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10043aa91  jz      short loc_10043AAC0
0x10043aa93  mov     [rsp+0A8h+var_78], r14d
0x10043aa98  mov     dword ptr [rsp+0A8h+var_80], r15d
0x10043aa9d  mov     dword ptr [rsp+0A8h+var_88], ebp
0x10043aaa1  lea     r9, aSniitemsProces; "SNIItems processed: %d, items closed: %"...
0x10043aaa8  mov     r8d, 1E6Dh; int
0x10043aaae  mov     rdx, r13; char *
0x10043aab1  mov     rcx, r12; char *
0x10043aab4  call    ?SNIXE_SNI_TRACE_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_TRACE_ON(char const *,char const *,int,wchar_t const *,...)
0x10043aab9  nop     dword ptr [rax+00000000h]
0x10043aac0  lea     rcx, [rsp+0A8h+ListHead]; ListHead
0x10043aac5  call    cs:__imp_InterlockedPopEntrySList
0x10043aacb  test    rax, rax
0x10043aace  jz      short loc_10043AAE2
0x10043aad0  mov     rdx, rax; ListEntry
0x10043aad3  lea     rcx, ?s_slhNotificationsToClose@Tcp@@1T_SLIST_HEADER@@A; ListHead
0x10043aada  call    cs:__imp_InterlockedPushEntrySList
0x10043aae0  jmp     short loc_10043AAC0
0x10043aae2  mov     ebx, 3
0x10043aae7  test    ebp, ebp
0x10043aae9  cmovnz  ebx, edi
0x10043aaec  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 80h; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10043aaf3  jz      short loc_10043AB06
0x10043aaf5  mov     r8d, 1E22h; int
0x10043aafb  mov     rdx, r13; char *
0x10043aafe  mov     rcx, r12; char *
0x10043ab01  call    ?SNIXE_SNI_LEAVE_ON@@YAXPEBD0HPEB_W@Z; SNIXE_SNI_LEAVE_ON(char const *,char const *,int,wchar_t const *)
0x10043ab06  mov     eax, ebx
0x10043ab08  mov     rcx, [rsp+0A8h+var_38]
0x10043ab0d  xor     rcx, rsp; StackCookie
0x10043ab10  call    __security_check_cookie
0x10043ab15  lea     r11, [rsp+0A8h+var_28]
0x10043ab1d  mov     rbx, [r11+30h]
0x10043ab21  mov     rbp, [r11+38h]
0x10043ab25  mov     rsi, [r11+40h]
0x10043ab29  mov     rsp, r11
0x10043ab2c  pop     r15
0x10043ab2e  pop     r14
0x10043ab30  pop     r13
0x10043ab32  pop     r12
0x10043ab34  pop     rdi
0x10043ab35  retn
```
