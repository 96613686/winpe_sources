# WlAccessibilityOnWinPlus(_WLSM_GLOBAL_CONTEXT *,int)

- ea: `0x1400594a4`
- end: `0x14005967b`
- name: `?WlAccessibilityOnWinPlus@@YAKPEAU_WLSM_GLOBAL_CONTEXT@@H@Z`
- size: `471`
- prototype: `__int64 __fastcall(struct _WLSM_GLOBAL_CONTEXT *, int)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140059928`

## callees

- `0x1400057f4`
- `0x14000d4e0`
- `0x140019b4c`
- `0x140019df8`
- `0x140041c34`
- `0x140053720`
- `0x1400594a4`
- `0x140094f68`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x1400594f1`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x1400594f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400594ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400594ff`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140059515`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140059515`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140059617`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140059617`

## string_xrefs

- `0x140059546`: `atbroker.exe`
- `0x1400594e1`: `MSScreenMagnifierAlreadyExistsMutex`

## pseudocode

```c
__int64 __fastcall WlAccessibilityOnWinPlus(struct _WLSM_GLOBAL_CONTEXT *a1, int a2)
{
  BOOL v4; // ebx
  HANDLE MutexW; // rsi
  unsigned int v6; // ebx
  __int64 v7; // r8
  CUser *v8; // rcx
  unsigned int started; // eax
  HKEY hKey; // [rsp+38h] [rbp-B0h] BYREF
  unsigned __int16 v12[64]; // [rsp+40h] [rbp-A8h] BYREF

  hKey = 0;
  v4 = 0;
  MutexW = CreateMutexW(0, 1, L"MSScreenMagnifierAlreadyExistsMutex");
  if ( MutexW )
  {
    v4 = GetLastError() == 183;
    CloseHandle(MutexW);
  }
  if ( v4 )
    goto LABEL_16;
  v6 = WlAccessibilityCreateSessionKeyWithPermissions(a1, &hKey);
  if ( v6 )
    goto LABEL_17;
  if ( (int)StringCchPrintfW(v12, 0x40u, L"%s %s", L"atbroker.exe", L"/start magnifierpane") >= 0 )
  {
    started = WlAccessibilitypStartProcessInAtJob((CSession **)a1, v12, v7, a2);
    v6 = started;
    if ( started )
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_18;
      }
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 92, WPP_08fbe39dfd5c3ed1d0f5d3aa8d6e811c_Traceguids, started);
LABEL_17:
      v8 = WPP_GLOBAL_Control;
      goto LABEL_18;
    }
LABEL_16:
    v6 = 0;
    goto LABEL_17;
  }
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), v6 + 91, WPP_08fbe39dfd5c3ed1d0f5d3aa8d6e811c_Traceguids);
    v8 = WPP_GLOBAL_Control;
  }
  v6 = 87;
LABEL_18:
  if ( hKey )
  {
    RegCloseKey(hKey);
    v8 = WPP_GLOBAL_Control;
  }
  if ( v8 != (CUser *)&WPP_GLOBAL_Control && (*((_DWORD *)v8 + 7) & 0x40000) != 0 && *((_BYTE *)v8 + 25) >= 4u )
    WPP_SF_d(*((_QWORD *)v8 + 2), 93, WPP_08fbe39dfd5c3ed1d0f5d3aa8d6e811c_Traceguids, v6);
  return v6;
}

```

## disassembly

```asm
0x1400594a4  mov     [rsp+arg_10], rbx
0x1400594a9  mov     [rsp+arg_18], rsi
0x1400594ae  push    rdi
0x1400594af  push    r14
0x1400594b1  push    r15
0x1400594b3  sub     rsp, 0D0h
0x1400594ba  mov     rax, cs:__security_cookie
0x1400594c1  xor     rax, rsp
0x1400594c4  mov     [rsp+0E8h+var_28], rax
0x1400594cc  mov     r14d, edx
0x1400594cf  mov     rdi, rcx
0x1400594d2  mov     [rsp+0E8h+hKey], 0
0x1400594db  xor     ebx, ebx
0x1400594dd  mov     [rsp+0E8h+var_B8], ebx
0x1400594e1  lea     r8, aMsscreenmagnif; "MSScreenMagnifierAlreadyExistsMutex"
0x1400594e8  lea     r15d, [rbx+1]
0x1400594ec  mov     edx, r15d; bInitialOwner
0x1400594ef  xor     ecx, ecx; lpMutexAttributes
0x1400594f1  call    cs:__imp_CreateMutexW
0x1400594f7  mov     rsi, rax
0x1400594fa  test    rax, rax
0x1400594fd  jz      short loc_14005951B
0x1400594ff  call    cs:__imp_GetLastError
0x140059505  cmp     eax, 0B7h
0x14005950a  cmovz   ebx, r15d
0x14005950e  mov     [rsp+0E8h+var_B8], ebx
0x140059512  mov     rcx, rsi; hObject
0x140059515  call    cs:__imp_CloseHandle
0x14005951b  test    ebx, ebx
0x14005951d  jnz     loc_1400595FA
0x140059523  lea     rdx, [rsp+0E8h+hKey]; HKEY *
0x140059528  mov     rcx, rdi; struct _WLSM_GLOBAL_CONTEXT *
0x14005952b  call    ?WlAccessibilityCreateSessionKeyWithPermissions@@YAKPEAU_WLSM_GLOBAL_CONTEXT@@PEAPEAUHKEY__@@@Z; WlAccessibilityCreateSessionKeyWithPermissions(_WLSM_GLOBAL_CONTEXT *,HKEY__ * *)
0x140059530  mov     ebx, eax
0x140059532  test    eax, eax
0x140059534  jnz     loc_1400595FC
0x14005953a  lea     rax, aStartMagnifier; "/start magnifierpane"
0x140059541  mov     [rsp+0E8h+var_C8], rax; void **
0x140059546  lea     r9, aAtbrokerExe; "atbroker.exe"
0x14005954d  lea     r8, aSS_0; "%s %s"
0x140059554  lea     edx, [rbx+40h]; unsigned __int64
0x140059557  lea     rcx, [rsp+0E8h+var_A8]; unsigned __int16 *
0x14005955c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140059561  test    eax, eax
0x140059563  jns     short loc_1400595A8
0x140059565  lea     rdi, WPP_GLOBAL_Control
0x14005956c  mov     rcx, cs:WPP_GLOBAL_Control
0x140059573  cmp     rcx, rdi
0x140059576  jz      short loc_1400595A1
0x140059578  test    dword ptr [rcx+1Ch], 40000h
0x14005957f  jz      short loc_1400595A1
0x140059581  cmp     byte ptr [rcx+19h], 2
0x140059585  jb      short loc_1400595A1
0x140059587  lea     edx, [rbx+5Bh]
0x14005958a  lea     r8, WPP_08fbe39dfd5c3ed1d0f5d3aa8d6e811c_Traceguids
0x140059591  mov     rcx, [rcx+10h]
0x140059595  call    WPP_SF_
0x14005959a  mov     rcx, cs:WPP_GLOBAL_Control
0x1400595a1  mov     ebx, 57h ; 'W'
0x1400595a6  jmp     short loc_14005960A
0x1400595a8  mov     r9d, r14d; int
0x1400595ab  lea     rdx, [rsp+0E8h+var_A8]; unsigned __int16 *
0x1400595b0  mov     rcx, rdi; struct _WLSM_GLOBAL_CONTEXT *
0x1400595b3  call    ?WlAccessibilitypStartProcessInAtJob@@YAKPEAU_WLSM_GLOBAL_CONTEXT@@PEBGKHPEAPEAX@Z; WlAccessibilitypStartProcessInAtJob(_WLSM_GLOBAL_CONTEXT *,ushort const *,ulong,int,void * *)
0x1400595b8  mov     ebx, eax
0x1400595ba  test    eax, eax
0x1400595bc  jz      short loc_1400595FA
0x1400595be  lea     rdi, WPP_GLOBAL_Control
0x1400595c5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400595cc  cmp     rcx, rdi
0x1400595cf  jz      short loc_14005960A
0x1400595d1  test    dword ptr [rcx+1Ch], 40000h
0x1400595d8  jz      short loc_14005960A
0x1400595da  cmp     byte ptr [rcx+19h], 2
0x1400595de  jb      short loc_14005960A
0x1400595e0  mov     edx, 5Ch ; '\'
0x1400595e5  mov     r9d, eax
0x1400595e8  lea     r8, WPP_08fbe39dfd5c3ed1d0f5d3aa8d6e811c_Traceguids
0x1400595ef  mov     rcx, [rcx+10h]
0x1400595f3  call    WPP_SF_d
0x1400595f8  jmp     short loc_140059603
0x1400595fa  xor     ebx, ebx
0x1400595fc  lea     rdi, WPP_GLOBAL_Control
0x140059603  mov     rcx, cs:WPP_GLOBAL_Control
0x14005960a  mov     rax, [rsp+0E8h+hKey]
0x14005960f  test    rax, rax
0x140059612  jz      short loc_140059624
0x140059614  mov     rcx, rax; hKey
0x140059617  call    cs:__imp_RegCloseKey
0x14005961d  mov     rcx, cs:WPP_GLOBAL_Control
0x140059624  cmp     rcx, rdi
0x140059627  jz      short loc_140059650
0x140059629  test    dword ptr [rcx+1Ch], 40000h
0x140059630  jz      short loc_140059650
0x140059632  cmp     byte ptr [rcx+19h], 4
0x140059636  jb      short loc_140059650
0x140059638  mov     edx, 5Dh ; ']'
0x14005963d  mov     r9d, ebx
0x140059640  lea     r8, WPP_08fbe39dfd5c3ed1d0f5d3aa8d6e811c_Traceguids
0x140059647  mov     rcx, [rcx+10h]
0x14005964b  call    WPP_SF_d
0x140059650  mov     eax, ebx
0x140059652  mov     rcx, [rsp+0E8h+var_28]
0x14005965a  xor     rcx, rsp; StackCookie
0x14005965d  call    __security_check_cookie
0x140059662  lea     r11, [rsp+0E8h+var_18]
0x14005966a  mov     rbx, [r11+30h]
0x14005966e  mov     rsi, [r11+38h]
0x140059672  mov     rsp, r11
0x140059675  pop     r15
0x140059677  pop     r14
0x140059679  pop     rdi
0x14005967a  retn
0x14009eb41  push    rbp
0x14009eb43  sub     rsp, 30h
0x14009eb47  mov     rbp, rdx
0x14009eb4a  mov     rcx, [rbp+38h]; hKey
0x14009eb4e  test    rcx, rcx
0x14009eb51  jz      short loc_14009EB5A
0x14009eb53  call    cs:__imp_RegCloseKey
0x14009eb59  nop
0x14009eb5a  add     rsp, 30h
0x14009eb5e  pop     rbp
0x14009eb5f  retn
```
