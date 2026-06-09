# OpenClientKeyHandle(ushort *,ushort *,ulong,ulong,ulong,unsigned __int64 *,unsigned __int64 *)

- ea: `0x18006daac`
- end: `0x18006ddc3`
- name: `?OpenClientKeyHandle@@YAJPEAG0KKKPEA_K1@Z`
- size: `791`
- prototype: `__int64 __fastcall(LPCWSTR pszKeyName, LPCWSTR pszProviderName, DWORD dwLegacyKeySpec, DWORD dwProvType, unsigned int, NCRYPT_KEY_HANDLE *phKey, HCRYPTPROV *phProv)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation`

## callers

- `0x18004dd80`
- `0x18006ee80`

## callees

- `0x180021da8`
- `0x18004a060`
- `0x180057c8c`
- `0x180057cb4`
- `0x18005c3a0`
- `0x18005edb8`
- `0x18006daac`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006dcbe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006dcbe`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18006dcc6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18006dcc6`
- `CRYPTSP!CryptAcquireContextW` at `0x18006dcb4`
- `CRYPTSP!CryptAcquireContextW` at `0x18006dcb4`

## pseudocode

```c
__int64 __fastcall OpenClientKeyHandle(
        LPCWSTR pszKeyName,
        LPCWSTR pszProviderName,
        DWORD dwLegacyKeySpec,
        DWORD dwProvType,
        unsigned int a5,
        NCRYPT_KEY_HANDLE *phKey,
        HCRYPTPROV *phProv)
{
  NCRYPT_KEY_HANDLE *v7; // rsi
  HCRYPTPROV *v12; // rbx
  CCipherMill *v13; // rcx
  const wchar_t *v14; // r9
  __int64 v15; // rcx
  const wchar_t *v16; // r9
  bool v17; // zf
  DWORD LastError; // edi
  DWORD CurrentProcessId; // eax
  CCipherMill *v21; // rcx

  v7 = phKey;
  if ( !phKey )
    return 2148074333LL;
  v12 = phProv;
  if ( !phProv )
    return 2148074333LL;
  *phKey = 0;
  *v12 = 0;
  v13 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      v14 = pszKeyName;
      if ( !pszKeyName )
        v14 = L"(null)";
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_afafbaf638ed37b28ae3c1cec484c558_Traceguids, v14);
      v13 = WPP_GLOBAL_Control;
    }
    if ( v13 != (CCipherMill *)&WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)v13 + 28) & 4) != 0 )
      {
        v15 = *((_QWORD *)v13 + 2);
        v16 = pszProviderName;
        if ( !pszProviderName )
          v16 = L"(null)";
        WPP_SF_S(v15, 11, WPP_afafbaf638ed37b28ae3c1cec484c558_Traceguids, v16);
        v13 = WPP_GLOBAL_Control;
      }
      if ( v13 != (CCipherMill *)&WPP_GLOBAL_Control )
      {
        if ( (*((_BYTE *)v13 + 28) & 4) != 0 )
        {
          WPP_SF_d(*((_QWORD *)v13 + 2), 12, WPP_afafbaf638ed37b28ae3c1cec484c558_Traceguids, dwLegacyKeySpec);
          v13 = WPP_GLOBAL_Control;
        }
        if ( v13 != (CCipherMill *)&WPP_GLOBAL_Control )
        {
          if ( (*((_BYTE *)v13 + 28) & 4) != 0 )
          {
            WPP_SF_d(*((_QWORD *)v13 + 2), 13, WPP_afafbaf638ed37b28ae3c1cec484c558_Traceguids, dwProvType);
            v13 = WPP_GLOBAL_Control;
          }
          if ( v13 != (CCipherMill *)&WPP_GLOBAL_Control && (*((_BYTE *)v13 + 28) & 4) != 0 )
            WPP_SF_d(*((_QWORD *)v13 + 2), 14, WPP_afafbaf638ed37b28ae3c1cec484c558_Traceguids, a5);
        }
      }
    }
  }
  LODWORD(phKey) = 0;
  if ( (unsigned int)OpenKeyUsingCng(v7, pszKeyName, pszProviderName, dwLegacyKeySpec, a5, 1, (int *)&phKey) )
  {
    v17 = (_DWORD)phKey == 0;
    *v7 = 0;
    if ( !v17 )
    {
      if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_afafbaf638ed37b28ae3c1cec484c558_Traceguids);
      return 2148074253LL;
    }
    if ( !CryptAcquireContextW(v12, pszKeyName, pszProviderName, dwProvType, a5 & 0xFFFFFFFE) )
    {
      LastError = GetLastError();
      CurrentProcessId = GetCurrentProcessId();
      LogCredAcquireContextFailedEvent(CurrentProcessId, L"<UNKNOWN>", 0, LastError, 10014);
      if ( LastError )
      {
        if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_afafbaf638ed37b28ae3c1cec484c558_Traceguids, LastError);
        *v12 = 0;
        return 2148074253LL;
      }
    }
  }
  v21 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_afafbaf638ed37b28ae3c1cec484c558_Traceguids);
      v21 = WPP_GLOBAL_Control;
    }
    if ( v21 != (CCipherMill *)&WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)v21 + 28) & 4) != 0 )
      {
        WPP_SF_q(*((_QWORD *)v21 + 2), 18, WPP_afafbaf638ed37b28ae3c1cec484c558_Traceguids, *v7);
        v21 = WPP_GLOBAL_Control;
      }
      if ( v21 != (CCipherMill *)&WPP_GLOBAL_Control && (*((_BYTE *)v21 + 28) & 4) != 0 )
        WPP_SF_q(*((_QWORD *)v21 + 2), 19, WPP_afafbaf638ed37b28ae3c1cec484c558_Traceguids, *v12);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18006daac  push    rbx
0x18006daae  push    rbp
0x18006daaf  push    rsi
0x18006dab0  push    rdi
0x18006dab1  push    r12
0x18006dab3  push    r14
0x18006dab5  push    r15
0x18006dab7  sub     rsp, 40h
0x18006dabb  mov     rsi, [rsp+78h+phKey]
0x18006dac3  mov     r12d, r9d
0x18006dac6  mov     r15d, r8d
0x18006dac9  mov     rbp, rdx
0x18006dacc  mov     r14, rcx
0x18006dacf  test    rsi, rsi
0x18006dad2  jz      loc_18006DDAF
0x18006dad8  mov     rbx, [rsp+78h+phProv]
0x18006dae0  test    rbx, rbx
0x18006dae3  jz      loc_18006DDAF
0x18006dae9  mov     qword ptr [rsi], 0
0x18006daf0  mov     qword ptr [rbx], 0
0x18006daf7  mov     rcx, cs:WPP_GLOBAL_Control
0x18006dafe  lea     rax, WPP_GLOBAL_Control
0x18006db05  mov     edi, [rsp+78h+arg_20]
0x18006db0c  cmp     rcx, rax
0x18006db0f  jz      loc_18006DC1B
0x18006db15  test    byte ptr [rcx+1Ch], 4
0x18006db19  lea     rdx, aNull_0; "(null)"
0x18006db20  jz      short loc_18006DB56
0x18006db22  mov     rcx, [rcx+10h]
0x18006db26  lea     r8, WPP_afafbaf638ed37b28ae3c1cec484c558_Traceguids
0x18006db2d  test    r14, r14
0x18006db30  mov     r9, r14
0x18006db33  cmovz   r9, rdx
0x18006db37  mov     edx, 0Ah
0x18006db3c  call    WPP_SF_S
0x18006db41  mov     rcx, cs:WPP_GLOBAL_Control
0x18006db48  lea     rax, WPP_GLOBAL_Control
0x18006db4f  lea     rdx, aNull_0; "(null)"
0x18006db56  cmp     rcx, rax
0x18006db59  jz      loc_18006DC1B
0x18006db5f  test    byte ptr [rcx+1Ch], 4
0x18006db63  jz      short loc_18006DB92
0x18006db65  mov     rcx, [rcx+10h]
0x18006db69  lea     r8, WPP_afafbaf638ed37b28ae3c1cec484c558_Traceguids
0x18006db70  test    rbp, rbp
0x18006db73  mov     r9, rbp
0x18006db76  cmovz   r9, rdx
0x18006db7a  mov     edx, 0Bh
0x18006db7f  call    WPP_SF_S
0x18006db84  mov     rcx, cs:WPP_GLOBAL_Control
0x18006db8b  lea     rax, WPP_GLOBAL_Control
0x18006db92  cmp     rcx, rax
0x18006db95  jz      loc_18006DC1B
0x18006db9b  test    byte ptr [rcx+1Ch], 4
0x18006db9f  jz      short loc_18006DBC7
0x18006dba1  mov     rcx, [rcx+10h]
0x18006dba5  lea     r8, WPP_afafbaf638ed37b28ae3c1cec484c558_Traceguids
0x18006dbac  mov     edx, 0Ch
0x18006dbb1  mov     r9d, r15d
0x18006dbb4  call    WPP_SF_d
0x18006dbb9  mov     rcx, cs:WPP_GLOBAL_Control
0x18006dbc0  lea     rax, WPP_GLOBAL_Control
0x18006dbc7  cmp     rcx, rax
0x18006dbca  jz      short loc_18006DC1B
0x18006dbcc  test    byte ptr [rcx+1Ch], 4
0x18006dbd0  jz      short loc_18006DBF8
0x18006dbd2  mov     rcx, [rcx+10h]
0x18006dbd6  lea     r8, WPP_afafbaf638ed37b28ae3c1cec484c558_Traceguids
0x18006dbdd  mov     edx, 0Dh
0x18006dbe2  mov     r9d, r12d
0x18006dbe5  call    WPP_SF_d
0x18006dbea  mov     rcx, cs:WPP_GLOBAL_Control
0x18006dbf1  lea     rax, WPP_GLOBAL_Control
0x18006dbf8  cmp     rcx, rax
0x18006dbfb  jz      short loc_18006DC1B
0x18006dbfd  test    byte ptr [rcx+1Ch], 4
0x18006dc01  jz      short loc_18006DC1B
0x18006dc03  mov     rcx, [rcx+10h]
0x18006dc07  lea     r8, WPP_afafbaf638ed37b28ae3c1cec484c558_Traceguids
0x18006dc0e  mov     edx, 0Eh
0x18006dc13  mov     r9d, edi
0x18006dc16  call    WPP_SF_d
0x18006dc1b  lea     rax, [rsp+78h+phKey]
0x18006dc23  mov     dword ptr [rsp+78h+phKey], 0
0x18006dc2e  mov     [rsp+78h+var_48], rax; int *
0x18006dc33  mov     r9d, r15d; dwLegacyKeySpec
0x18006dc36  mov     [rsp+78h+var_50], 1; int
0x18006dc3e  mov     r8, rbp; pszProviderName
0x18006dc41  mov     rdx, r14; pszKeyName
0x18006dc44  mov     [rsp+78h+dwFlags], edi; unsigned int
0x18006dc48  mov     rcx, rsi; phKey
0x18006dc4b  call    ?OpenKeyUsingCng@@YAKPEA_KPEBG1KKHPEAH@Z; OpenKeyUsingCng(unsigned __int64 *,ushort const *,ushort const *,ulong,ulong,int,int *)
0x18006dc50  test    eax, eax
0x18006dc52  jz      loc_18006DD29
0x18006dc58  cmp     dword ptr [rsp+78h+phKey], 0
0x18006dc60  mov     qword ptr [rsi], 0
0x18006dc67  jz      short loc_18006DCA1
0x18006dc69  mov     rcx, cs:WPP_GLOBAL_Control
0x18006dc70  lea     rbp, WPP_GLOBAL_Control
0x18006dc77  cmp     rcx, rbp
0x18006dc7a  jz      short loc_18006DC97
0x18006dc7c  test    byte ptr [rcx+1Ch], 4
0x18006dc80  jz      short loc_18006DC97
0x18006dc82  mov     rcx, [rcx+10h]
0x18006dc86  lea     r8, WPP_afafbaf638ed37b28ae3c1cec484c558_Traceguids
0x18006dc8d  mov     edx, 0Fh
0x18006dc92  call    WPP_SF_
0x18006dc97  mov     eax, 8009030Dh
0x18006dc9c  jmp     loc_18006DDB4
0x18006dca1  and     edi, 0FFFFFFFEh
0x18006dca4  mov     r9d, r12d; dwProvType
0x18006dca7  mov     r8, rbp; szProvider
0x18006dcaa  mov     [rsp+78h+dwFlags], edi; dwFlags
0x18006dcae  mov     rdx, r14; szContainer
0x18006dcb1  mov     rcx, rbx; phProv
0x18006dcb4  call    cs:__imp_CryptAcquireContextW
0x18006dcba  test    eax, eax
0x18006dcbc  jnz     short loc_18006DD29
0x18006dcbe  call    cs:__imp_GetLastError
0x18006dcc4  mov     edi, eax
0x18006dcc6  call    cs:__imp_GetCurrentProcessId
0x18006dccc  mov     r9d, edi
0x18006dccf  mov     [rsp+78h+dwFlags], 271Eh
0x18006dcd7  mov     ecx, eax
0x18006dcd9  lea     rdx, aUnknown_0; "<UNKNOWN>"
0x18006dce0  xor     r8d, r8d
0x18006dce3  call    ?LogCredAcquireContextFailedEvent@@YAXKPEBGEKW4eSslErrorState@@@Z; LogCredAcquireContextFailedEvent(ulong,ushort const *,uchar,ulong,eSslErrorState)
0x18006dce8  test    edi, edi
0x18006dcea  jz      short loc_18006DD29
0x18006dcec  mov     rcx, cs:WPP_GLOBAL_Control
0x18006dcf3  lea     rbp, WPP_GLOBAL_Control
0x18006dcfa  cmp     rcx, rbp
0x18006dcfd  jz      short loc_18006DD1D
0x18006dcff  test    byte ptr [rcx+1Ch], 1
0x18006dd03  jz      short loc_18006DD1D
0x18006dd05  mov     rcx, [rcx+10h]
0x18006dd09  lea     r8, WPP_afafbaf638ed37b28ae3c1cec484c558_Traceguids
0x18006dd10  mov     edx, 10h
0x18006dd15  mov     r9d, edi
0x18006dd18  call    WPP_SF_d
0x18006dd1d  mov     qword ptr [rbx], 0
0x18006dd24  jmp     loc_18006DC97
0x18006dd29  mov     rcx, cs:WPP_GLOBAL_Control
0x18006dd30  lea     rbp, WPP_GLOBAL_Control
0x18006dd37  cmp     rcx, rbp
0x18006dd3a  jz      short loc_18006DDAB
0x18006dd3c  test    byte ptr [rcx+1Ch], 4
0x18006dd40  jz      short loc_18006DD5E
0x18006dd42  mov     rcx, [rcx+10h]
0x18006dd46  lea     r8, WPP_afafbaf638ed37b28ae3c1cec484c558_Traceguids
0x18006dd4d  mov     edx, 11h
0x18006dd52  call    WPP_SF_
0x18006dd57  mov     rcx, cs:WPP_GLOBAL_Control
0x18006dd5e  cmp     rcx, rbp
0x18006dd61  jz      short loc_18006DDAB
0x18006dd63  test    byte ptr [rcx+1Ch], 4
0x18006dd67  jz      short loc_18006DD88
0x18006dd69  mov     r9, [rsi]
0x18006dd6c  lea     r8, WPP_afafbaf638ed37b28ae3c1cec484c558_Traceguids
0x18006dd73  mov     rcx, [rcx+10h]
0x18006dd77  mov     edx, 12h
0x18006dd7c  call    WPP_SF_q
0x18006dd81  mov     rcx, cs:WPP_GLOBAL_Control
0x18006dd88  cmp     rcx, rbp
0x18006dd8b  jz      short loc_18006DDAB
0x18006dd8d  test    byte ptr [rcx+1Ch], 4
0x18006dd91  jz      short loc_18006DDAB
0x18006dd93  mov     r9, [rbx]
0x18006dd96  lea     r8, WPP_afafbaf638ed37b28ae3c1cec484c558_Traceguids
0x18006dd9d  mov     rcx, [rcx+10h]
0x18006dda1  mov     edx, 13h
0x18006dda6  call    WPP_SF_q
0x18006ddab  xor     eax, eax
0x18006ddad  jmp     short loc_18006DDB4
0x18006ddaf  mov     eax, 8009035Dh
0x18006ddb4  add     rsp, 40h
0x18006ddb8  pop     r15
0x18006ddba  pop     r14
0x18006ddbc  pop     r12
0x18006ddbe  pop     rdi
0x18006ddbf  pop     rsi
0x18006ddc0  pop     rbp
0x18006ddc1  pop     rbx
0x18006ddc2  retn
```
