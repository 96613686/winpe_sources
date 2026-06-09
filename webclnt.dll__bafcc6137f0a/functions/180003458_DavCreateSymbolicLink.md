# DavCreateSymbolicLink

- ea: `0x180003458`
- end: `0x180003705`
- name: `DavCreateSymbolicLink`
- size: `685`
- prototype: `__int64 __fastcall(const WCHAR *, const WCHAR *, __int64 *, void **)`
- caller_count: `1`
- callee_count: `8`
- tags: `reparse_path, authz_impersonation`

## callers

- `0x180006d20`

## callees

- `0x180003458`
- `0x18000591c`
- `0x18000656c`
- `0x180006618`
- `0x18000b7b4`
- `0x18000b7dc`
- `0x18000b93c`
- `0x18002cfa0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800034b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003567`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800035ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000365f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800034b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003567`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800035ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000365f`
- `api-ms-win-core-file-l1-1-0!DefineDosDeviceW` at `0x180003655`
- `api-ms-win-core-file-l1-1-0!DefineDosDeviceW` at `0x180003655`
- `api-ms-win-core-file-l1-1-0!QueryDosDeviceW` at `0x1800035f1`
- `api-ms-win-core-file-l1-1-0!QueryDosDeviceW` at `0x1800035f1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180003546`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180003546`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000355d`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000355d`

## pseudocode

```c
__int64 __fastcall DavCreateSymbolicLink(const WCHAR *a1, const WCHAR *a2, __int64 *a3, void **a4)
{
  const WCHAR *v7; // rsi
  __int64 v8; // rax
  unsigned int LastError; // eax
  unsigned int v10; // ebx
  _QWORD *v11; // rcx
  __int64 v12; // rdx
  int v13; // ebp
  HANDLE CurrentThread; // rax
  DWORD v15; // eax
  _QWORD *v16; // rcx
  __int64 v17; // rdx
  __int64 v18; // r9
  DWORD v19; // eax
  unsigned int v20; // eax
  unsigned int v21; // esi
  void *TokenHandle; // [rsp+20h] [rbp-D8h] BYREF
  WCHAR TargetPath[64]; // [rsp+30h] [rbp-C8h] BYREF

  TokenHandle = 0;
  v7 = a1;
  if ( !g_LUIDDeviceMapsEnabled )
  {
    if ( !a3 || !a1 )
      return 87;
    v8 = DavReturnSessionPath();
    *a3 = v8;
    v7 = (const WCHAR *)v8;
    if ( !v8 )
    {
      LastError = GetLastError();
      v10 = LastError;
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v12 = 215;
LABEL_8:
        WPP_SF_d(v11[2], v12, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids, LastError);
        return v10;
      }
      return v10;
    }
    v13 = 0;
    v10 = 0;
    goto LABEL_22;
  }
  LastError = DavImpersonateClient();
  v10 = LastError;
  if ( !LastError )
  {
    if ( a4 )
    {
      CurrentThread = GetCurrentThread();
      if ( !OpenThreadToken(CurrentThread, 4u, 1, &TokenHandle) )
      {
        v15 = GetLastError();
        v10 = v15;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 217, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids, v15);
LABEL_41:
        v20 = DavRevertToSelf();
        v21 = v20;
        if ( v20 )
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 222, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids, v20);
          return v21;
        }
        return v10;
      }
      *a4 = TokenHandle;
    }
    v13 = 1;
LABEL_22:
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 218, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids, v7);
    if ( QueryDosDeviceW(v7, TargetPath, 0x40u) )
    {
      v10 = 85;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 220, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids);
    }
    else if ( GetLastError() == 2 )
    {
      if ( a2 )
      {
        if ( !DefineDosDeviceW(9u, v7, a2) )
        {
          v19 = GetLastError();
          v10 = v19;
          v16 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v17 = 221;
            v18 = v19;
            goto LABEL_30;
          }
        }
      }
      else
      {
        v10 = 87;
      }
    }
    else
    {
      v10 = 85;
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v17 = 219;
        v18 = 85;
LABEL_30:
        WPP_SF_d(v16[2], v17, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids, v18);
      }
    }
    if ( v13 != 1 )
      return v10;
    goto LABEL_41;
  }
  v11 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v12 = 216;
    goto LABEL_8;
  }
  return v10;
}

```

## disassembly

```asm
0x180003458  push    rbx
0x18000345a  push    rbp
0x18000345b  push    rsi
0x18000345c  push    rdi
0x18000345d  push    r12
0x18000345f  push    r14
0x180003461  sub     rsp, 0C8h
0x180003468  mov     rax, cs:__security_cookie
0x18000346f  xor     rax, rsp
0x180003472  mov     [rsp+0F8h+var_48], rax
0x18000347a  cmp     cs:g_LUIDDeviceMapsEnabled, 0
0x180003481  lea     r12, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids
0x180003488  mov     rdi, r9
0x18000348b  mov     [rsp+0F8h+TokenHandle], 0
0x180003494  mov     rbx, r8
0x180003497  mov     r14, rdx
0x18000349a  mov     rsi, rcx
0x18000349d  jnz     short loc_18000350E
0x18000349f  test    rbx, rbx
0x1800034a2  jz      short loc_180003504
0x1800034a4  test    rcx, rcx
0x1800034a7  jz      short loc_180003504
0x1800034a9  call    DavReturnSessionPath
0x1800034ae  mov     [rbx], rax
0x1800034b1  mov     rsi, rax
0x1800034b4  test    rax, rax
0x1800034b7  jnz     short loc_1800034FB
0x1800034b9  call    cs:__imp_GetLastError
0x1800034bf  mov     ebx, eax
0x1800034c1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800034c8  lea     rdi, WPP_GLOBAL_Control
0x1800034cf  cmp     rcx, rdi
0x1800034d2  jz      loc_1800036E3
0x1800034d8  test    byte ptr [rcx+1Ch], 1
0x1800034dc  jz      loc_1800036E3
0x1800034e2  mov     edx, 0D7h
0x1800034e7  mov     rcx, [rcx+10h]
0x1800034eb  mov     r9d, eax
0x1800034ee  mov     r8, r12
0x1800034f1  call    WPP_SF_d
0x1800034f6  jmp     loc_1800036E3
0x1800034fb  xor     ebp, ebp
0x1800034fd  xor     ebx, ebx
0x1800034ff  jmp     loc_1800035B6
0x180003504  mov     ebx, 57h ; 'W'
0x180003509  jmp     loc_1800036E3
0x18000350e  call    DavImpersonateClient
0x180003513  mov     ebx, eax
0x180003515  test    eax, eax
0x180003517  jz      short loc_180003541
0x180003519  mov     rcx, cs:WPP_GLOBAL_Control
0x180003520  lea     rdi, WPP_GLOBAL_Control
0x180003527  cmp     rcx, rdi
0x18000352a  jz      loc_1800036E3
0x180003530  test    byte ptr [rcx+1Ch], 1
0x180003534  jz      loc_1800036E3
0x18000353a  mov     edx, 0D8h
0x18000353f  jmp     short loc_1800034E7
0x180003541  test    rdi, rdi
0x180003544  jz      short loc_1800035B1
0x180003546  call    cs:__imp_GetCurrentThread
0x18000354c  mov     edx, 4; DesiredAccess
0x180003551  lea     r9, [rsp+0F8h+TokenHandle]; TokenHandle
0x180003556  mov     rcx, rax; ThreadHandle
0x180003559  lea     r8d, [rdx-3]; OpenAsSelf
0x18000355d  call    cs:__imp_OpenThreadToken
0x180003563  test    eax, eax
0x180003565  jnz     short loc_1800035A9
0x180003567  call    cs:__imp_GetLastError
0x18000356d  mov     ebx, eax
0x18000356f  mov     rcx, cs:WPP_GLOBAL_Control
0x180003576  lea     rdi, WPP_GLOBAL_Control
0x18000357d  cmp     rcx, rdi
0x180003580  jz      loc_1800036B0
0x180003586  test    byte ptr [rcx+1Ch], 1
0x18000358a  jz      loc_1800036B0
0x180003590  mov     rcx, [rcx+10h]
0x180003594  mov     edx, 0D9h
0x180003599  mov     r9d, eax
0x18000359c  mov     r8, r12
0x18000359f  call    WPP_SF_d
0x1800035a4  jmp     loc_1800036B0
0x1800035a9  mov     rax, [rsp+0F8h+TokenHandle]
0x1800035ae  mov     [rdi], rax
0x1800035b1  mov     ebp, 1
0x1800035b6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800035bd  lea     rdi, WPP_GLOBAL_Control
0x1800035c4  cmp     rcx, rdi
0x1800035c7  jz      short loc_1800035E3
0x1800035c9  test    byte ptr [rcx+1Ch], 2
0x1800035cd  jz      short loc_1800035E3
0x1800035cf  mov     rcx, [rcx+10h]
0x1800035d3  mov     edx, 0DAh
0x1800035d8  mov     r9, rsi
0x1800035db  mov     r8, r12
0x1800035de  call    WPP_SF_S
0x1800035e3  mov     r8d, 40h ; '@'; ucchMax
0x1800035e9  lea     rdx, [rsp+0F8h+TargetPath]; lpTargetPath
0x1800035ee  mov     rcx, rsi; lpDeviceName
0x1800035f1  call    cs:__imp_QueryDosDeviceW
0x1800035f7  test    eax, eax
0x1800035f9  jnz     loc_180003683
0x1800035ff  call    cs:__imp_GetLastError
0x180003605  cmp     eax, 2
0x180003608  jz      short loc_18000363F
0x18000360a  mov     ebx, 55h ; 'U'
0x18000360f  mov     rcx, cs:WPP_GLOBAL_Control
0x180003616  cmp     rcx, rdi
0x180003619  jz      loc_1800036AB
0x18000361f  test    byte ptr [rcx+1Ch], 1
0x180003623  jz      loc_1800036AB
0x180003629  mov     edx, 0DBh
0x18000362e  mov     r9d, ebx
0x180003631  mov     rcx, [rcx+10h]
0x180003635  mov     r8, r12
0x180003638  call    WPP_SF_d
0x18000363d  jmp     short loc_1800036AB
0x18000363f  test    r14, r14
0x180003642  jnz     short loc_18000364A
0x180003644  lea     ebx, [r14+57h]
0x180003648  jmp     short loc_1800036AB
0x18000364a  mov     r8, r14; lpTargetPath
0x18000364d  mov     rdx, rsi; lpDeviceName
0x180003650  mov     ecx, 9; dwFlags
0x180003655  call    cs:__imp_DefineDosDeviceW
0x18000365b  test    eax, eax
0x18000365d  jnz     short loc_1800036AB
0x18000365f  call    cs:__imp_GetLastError
0x180003665  mov     ebx, eax
0x180003667  mov     rcx, cs:WPP_GLOBAL_Control
0x18000366e  cmp     rcx, rdi
0x180003671  jz      short loc_1800036AB
0x180003673  test    byte ptr [rcx+1Ch], 1
0x180003677  jz      short loc_1800036AB
0x180003679  mov     edx, 0DDh
0x18000367e  mov     r9d, eax
0x180003681  jmp     short loc_180003631
0x180003683  mov     ebx, 55h ; 'U'
0x180003688  mov     rcx, cs:WPP_GLOBAL_Control
0x18000368f  cmp     rcx, rdi
0x180003692  jz      short loc_1800036AB
0x180003694  test    byte ptr [rcx+1Ch], 1
0x180003698  jz      short loc_1800036AB
0x18000369a  mov     rcx, [rcx+10h]
0x18000369e  mov     edx, 0DCh
0x1800036a3  mov     r8, r12
0x1800036a6  call    WPP_SF_
0x1800036ab  cmp     ebp, 1
0x1800036ae  jnz     short loc_1800036E3
0x1800036b0  call    DavRevertToSelf
0x1800036b5  mov     esi, eax
0x1800036b7  test    eax, eax
0x1800036b9  jz      short loc_1800036E3
0x1800036bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800036c2  cmp     rcx, rdi
0x1800036c5  jz      short loc_1800036E1
0x1800036c7  test    byte ptr [rcx+1Ch], 1
0x1800036cb  jz      short loc_1800036E1
0x1800036cd  mov     rcx, [rcx+10h]
0x1800036d1  mov     edx, 0DEh
0x1800036d6  mov     r9d, eax
0x1800036d9  mov     r8, r12
0x1800036dc  call    WPP_SF_d
0x1800036e1  mov     ebx, esi
0x1800036e3  mov     eax, ebx
0x1800036e5  mov     rcx, [rsp+0F8h+var_48]
0x1800036ed  xor     rcx, rsp; StackCookie
0x1800036f0  call    __security_check_cookie
0x1800036f5  add     rsp, 0C8h
0x1800036fc  pop     r14
0x1800036fe  pop     r12
0x180003700  pop     rdi
0x180003701  pop     rsi
0x180003702  pop     rbp
0x180003703  pop     rbx
0x180003704  retn
```
