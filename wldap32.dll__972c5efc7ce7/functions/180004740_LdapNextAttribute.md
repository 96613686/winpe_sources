# LdapNextAttribute

- ea: `0x180004740`
- end: `0x180004e4c`
- name: `LdapNextAttribute`
- size: `1804`
- prototype: ``
- caller_count: `6`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x18000461c`
- `0x1800057a0`
- `0x1800188d0`
- `0x18001b0d4`
- `0x18002bd70`
- `0x18002cdd0`

## callees

- `0x180001790`
- `0x180001820`
- `0x1800032d0`
- `0x180003570`
- `0x1800037a8`
- `0x180004740`
- `0x180005134`
- `0x180006510`
- `0x18000da50`
- `0x18001ce90`
- `0x18001e2c0`
- `0x180027530`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800047b4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800047b4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800047d4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800047d4`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180004b18`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180004b18`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004777`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004777`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000478b`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180004a21`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000478b`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180004a21`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18000498b`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18000498b`

## string_xrefs

- `0x180004beb`: `ldapNextAttr could not find ThreadEntry for connection 0x%x, thread 0x%x.  Creating one.\n`
- `0x180004c30`: `ldapNextAttr AddPerThreadEntry failed, connection 0x%x, thread 0x%x.\n`
- `0x180004c77`: `ldapNextAttr no per-thread entry, connection 0x%x, thread 0x%x.\n`
- `0x180004d04`: `ldapNextAttr 1 connection 0x%x received protocol error 0x%x .\n`
- `0x180004d3e`: `ldapNextAttr 5 connection 0x%x received protocol error 0x%x .\n`
- `0x180004a06`: `ldapNextAttr 2 connection 0x%x received protocol error 0x%x .\n`
- `0x180004e23`: `ldapNextAttr 3 connection 0x%x received protocol error 0x%x .\n`
- `0x180004b87`: `HrStartReadSequence ran out of data, length 0x%x, offset 0x%x.\n`
- `0x180004bad`: `HrStartReadSequence expected tag of 0x%x, received 0x%x.\n`
- `0x180004dbe`: `HrStartReadSequence 2 ran out of data, length 0x%x, offset 0x%x.\n`

## pseudocode

```c
__int64 *__fastcall LdapNextAttribute(__int64 a1, __int64 a2, unsigned int *a3, char a4)
{
  __int64 *v7; // r14
  DWORD CurrentThreadId; // ebp
  _QWORD *Value; // rax
  __int64 CurrentPerThreadEntry; // rdi
  __int64 *i; // rdi
  unsigned int Length; // ebp
  PCHAR v13; // rax
  unsigned int v14; // eax
  int v15; // r8d
  int v16; // r15d
  unsigned int Sequence; // eax
  __int64 v18; // rcx
  unsigned int v19; // edx
  __int64 v20; // r9
  int v21; // r8d
  __int64 v22; // r8
  char v23; // cl
  unsigned int v24; // r9d
  __int64 v25; // rax
  unsigned int v26; // ecx
  unsigned int v27; // edx
  unsigned int v28; // eax
  int v29; // eax
  _DWORD *v31; // r15
  _DWORD *v32; // rax
  const char *v33; // rdx
  unsigned __int8 lpMultiByteStr; // [rsp+20h] [rbp-58h]
  unsigned int v35[4]; // [rsp+40h] [rbp-38h] BYREF
  unsigned int v36; // [rsp+88h] [rbp+10h] BYREF

  if ( a2 && *(_DWORD *)(a2 + 4) == 100 )
  {
    v7 = 0;
    CurrentThreadId = GetCurrentThreadId();
    Value = TlsGetValue(GlobalTlsLastErrorIndex);
    if ( !Value || (CurrentPerThreadEntry = Value[1]) == 0 )
    {
      if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x400000) != 0 )
        LDAPClientPrint(
          0x400000,
          "ldapNextAttr could not find ThreadEntry for connection 0x%x, thread 0x%x.  Creating one.\n",
          a1,
          CurrentThreadId);
      if ( !(unsigned int)AddPerThreadEntry(CurrentThreadId) )
      {
        if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x400000) != 0 )
          LDAPClientPrint(
            0x400000,
            "ldapNextAttr AddPerThreadEntry failed, connection 0x%x, thread 0x%x.\n",
            a1,
            CurrentThreadId);
        SetConnectionError(a1, 90);
        return v7;
      }
      CurrentPerThreadEntry = GetCurrentPerThreadEntry();
      if ( !CurrentPerThreadEntry )
      {
        if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x400000) != 0 )
          LDAPClientPrint(
            0x400000,
            "ldapNextAttr no per-thread entry, connection 0x%x, thread 0x%x.\n",
            a1,
            CurrentThreadId);
        goto LABEL_57;
      }
    }
    EnterCriticalSection(&PerThreadListLock);
    for ( i = *(__int64 **)(CurrentPerThreadEntry + 32); i; i = (__int64 *)*i )
    {
      if ( i[2] == a1 )
        break;
    }
    LeaveCriticalSection(&PerThreadListLock);
    if ( !i )
      goto LABEL_57;
    Length = 16;
    if ( GlobalTlsLastErrorIndex != -1 )
    {
      v31 = TlsGetValue(GlobalTlsLastErrorIndex);
      if ( !v31 )
      {
        v32 = (_DWORD *)ldapMalloc(16, 1817471076);
        v31 = v32;
        if ( !v32 )
          goto LABEL_8;
        TlsSetValue(GlobalTlsLastErrorIndex, v32);
      }
      *v31 = 0;
    }
LABEL_8:
    if ( a1 )
    {
      *(_DWORD *)(a1 + 1020) = 0;
      v13 = ldap_err2string(0);
      *(_QWORD *)(a1 + 1032) = v13;
      *(_QWORD *)(a1 + 1024) = 0;
      if ( !*v13 )
      {
        if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x8000000) != 0 )
          LDAPClientPrint(0x8000000, "ldap SetConnectionError does not have text for message 0x%x.\n", 0);
        *(_QWORD *)(a1 + 1032) = ldap_err2string(0x50u);
      }
    }
    if ( a3 )
    {
      v14 = a3[1];
      v15 = *a3;
      if ( *a3 > v14 )
      {
        v16 = *(unsigned __int8 *)(v14 + *((_QWORD *)a3 + 2));
        if ( v16 != 49 )
        {
LABEL_13:
          Sequence = CLdapBer::HrEndReadSequence((CLdapBer *)a3);
          if ( Sequence && g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x400000) != 0 )
            LDAPClientPrint(0x400000, "ldapNextAttr 5 connection 0x%x received protocol error 0x%x .\n", a1, Sequence);
          if ( v16 != 48 )
            return v7;
          v18 = a3[1];
          v19 = *a3;
          if ( *a3 > (unsigned int)v18 )
          {
            v20 = *((_QWORD *)a3 + 2);
            v21 = *(unsigned __int8 *)(v18 + v20);
            if ( (_BYTE)v21 == 48 )
            {
              v22 = (unsigned int)(v18 + 1);
              a3[1] = v22;
              if ( v19 > (unsigned int)v22 )
              {
                v23 = *(_BYTE *)(v22 + v20);
                v24 = 1;
                if ( v23 < 0 )
                  v24 = (v23 & 0x7F) + 1;
                v25 = a3[8];
                if ( (unsigned int)v25 >= 0x32 )
                {
                  Length = -2147024882;
                }
                else
                {
                  v26 = a3[210];
                  v27 = a3[209];
                  a3[4 * v25 + 9] = v22;
                  a3[4 * a3[8] + 10] = v24;
                  a3[4 * a3[8] + 11] = v26;
                  a3[4 * a3[8]++ + 12] = v27;
                  Length = CLdapBer::HrGetLength((CLdapBer *)a3, a3 + 209);
                  if ( Length )
                    CLdapBer::HrPopSeqStack((CLdapBer *)a3, v35, &v36, a3 + 210, a3 + 209);
                  else
                    a3[210] = a3[1];
                }
                if ( a3[1] > *a3 )
                {
                  Length = -2147024809;
                }
                else if ( !Length )
                {
                  v28 = CLdapBer::HrGetValue((CLdapBer *)a3, (unsigned __int16 *)i + 420, v22, v24, lpMultiByteStr);
                  if ( !v28 )
                  {
                    v29 = WideCharToMultiByte(0, 0x400u, (LPCWCH)i + 420, -1, (LPSTR)i + 32, 799, 0, 0);
                    if ( v29 )
                    {
                      *((_BYTE *)i + (unsigned int)(v29 - 1) + 32) = 0;
                      v7 = i + 4;
                      if ( a4 )
                        return i + 105;
                    }
                    else
                    {
                      SetConnectionError(a1, 90);
                    }
                    return v7;
                  }
                  if ( !g_fTracingOn || !g_fProviderEnabled || (g_ulTraceFlags & 0x400000) == 0 )
                    goto LABEL_104;
                  v33 = "ldapNextAttr 3 connection 0x%x received protocol error 0x%x .\n";
LABEL_103:
                  LDAPClientPrint(0x400000, v33, a1, v28);
                  goto LABEL_104;
                }
LABEL_30:
                if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x400000) != 0 )
                  LDAPClientPrint(
                    0x400000,
                    "ldapNextAttr 2 connection 0x%x received protocol error 0x%x .\n",
                    a1,
                    Length);
                goto LABEL_104;
              }
              if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x2000) != 0 )
              {
                LDAPClientPrint(0x2000, "HrStartReadSequence 2 ran out of data, length 0x%x, offset 0x%x.\n", v19, v22);
                Length = -2147024809;
                goto LABEL_30;
              }
            }
            else if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x2000) != 0 )
            {
              LDAPClientPrint(0x2000, "HrStartReadSequence expected tag of 0x%x, received 0x%x.\n", 48, v21);
            }
            Length = -2147024809;
            goto LABEL_30;
          }
          if ( !g_fTracingOn )
          {
LABEL_104:
            SetConnectionError(a1, 84);
            return v7;
          }
          if ( g_fProviderEnabled && (g_ulTraceFlags & 0x2000) != 0 )
            LDAPClientPrint(0x2000, "HrStartReadSequence ran out of data, length 0x%x, offset 0x%x.\n", v19, v18);
          goto LABEL_30;
        }
        v28 = CLdapBer::HrSkipElement((CLdapBer *)a3);
        if ( v28 )
        {
          if ( !g_fTracingOn || !g_fProviderEnabled || (g_ulTraceFlags & 0x400000) == 0 )
            goto LABEL_104;
          v33 = "ldapNextAttr 1 connection 0x%x received protocol error 0x%x .\n";
          goto LABEL_103;
        }
        v14 = a3[1];
        v15 = *a3;
        if ( *a3 > v14 )
        {
          v16 = *(unsigned __int8 *)(v14 + *((_QWORD *)a3 + 2));
          goto LABEL_13;
        }
      }
      if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x2000) != 0 )
        LDAPClientPrint(0x2000, "HrPeekTag ran out of data, length 0x%x, offset 0x%x.\n", v15, v14);
      return v7;
    }
LABEL_57:
    SetConnectionError(a1, 82);
    return v7;
  }
  SetConnectionError(a1, 84);
  return 0;
}

```

## disassembly

```asm
0x180004740  mov     rax, rsp
0x180004743  push    rbx
0x180004744  push    rsi
0x180004745  push    r13
0x180004747  sub     rsp, 60h
0x18000474b  movzx   r13d, r9b
0x18000474f  mov     rbx, r8
0x180004752  mov     rsi, rcx
0x180004755  test    rdx, rdx
0x180004758  jz      loc_180004AA2
0x18000475e  cmp     dword ptr [rdx+4], 64h ; 'd'
0x180004762  jnz     loc_180004AA2
0x180004768  mov     [rax+8], rbp
0x18000476c  mov     [rax-20h], r14
0x180004770  xor     r14d, r14d
0x180004773  mov     [rax+18h], rdi
0x180004777  call    cs:__imp_GetCurrentThreadId
0x18000477e  nop     dword ptr [rax+rax+00h]
0x180004783  mov     ecx, cs:GlobalTlsLastErrorIndex; dwTlsIndex
0x180004789  mov     ebp, eax
0x18000478b  call    cs:__imp_TlsGetValue
0x180004792  nop     dword ptr [rax+rax+00h]
0x180004797  test    rax, rax
0x18000479a  jz      loc_180004BC9
0x1800047a0  mov     rdi, [rax+8]
0x1800047a4  test    rdi, rdi
0x1800047a7  jz      loc_180004BC9
0x1800047ad  lea     rcx, PerThreadListLock; lpCriticalSection
0x1800047b4  call    cs:__imp_EnterCriticalSection
0x1800047bb  nop     dword ptr [rax+rax+00h]
0x1800047c0  mov     rdi, [rdi+20h]
0x1800047c4  test    rdi, rdi
0x1800047c7  jnz     loc_180004A60
0x1800047cd  lea     rcx, PerThreadListLock; lpCriticalSection
0x1800047d4  call    cs:__imp_LeaveCriticalSection
0x1800047db  nop     dword ptr [rax+rax+00h]
0x1800047e0  test    rdi, rdi
0x1800047e3  jz      loc_180004B5E
0x1800047e9  mov     ecx, cs:GlobalTlsLastErrorIndex; dwTlsIndex
0x1800047ef  mov     ebp, 10h
0x1800047f4  mov     [rsp+78h+var_28], r15
0x1800047f9  cmp     ecx, 0FFFFFFFFh
0x1800047fc  jnz     loc_180004A21
0x180004802  test    rsi, rsi
0x180004805  jz      short loc_18000482C
0x180004807  xor     ecx, ecx; err
0x180004809  mov     [rsi+3FCh], r14d
0x180004810  call    ldap_err2string
0x180004815  mov     [rsi+408h], rax
0x18000481c  mov     [rsi+400h], r14
0x180004823  cmp     [rax], r14b
0x180004826  jz      loc_180004C90
0x18000482c  test    rbx, rbx
0x18000482f  jz      loc_180004A12
0x180004835  mov     eax, [rbx+4]
0x180004838  mov     r8d, [rbx]
0x18000483b  cmp     r8d, eax
0x18000483e  jbe     loc_180004AB3
0x180004844  mov     ecx, eax
0x180004846  mov     rax, [rbx+10h]
0x18000484a  movzx   r15d, byte ptr [rcx+rax]
0x18000484f  cmp     r15d, 31h ; '1'
0x180004853  jz      loc_180004A77
0x180004859  mov     rcx, rbx; this
0x18000485c  call    ?HrEndReadSequence@CLdapBer@@QEAAKXZ; CLdapBer::HrEndReadSequence(void)
0x180004861  test    eax, eax
0x180004863  jnz     loc_180004D10
0x180004869  cmp     r15d, 30h ; '0'
0x18000486d  jnz     loc_1800049AC
0x180004873  mov     ecx, [rbx+4]
0x180004876  mov     edx, [rbx]
0x180004878  cmp     edx, ecx
0x18000487a  jbe     loc_180004D57
0x180004880  mov     r9, [rbx+10h]
0x180004884  movzx   r8d, byte ptr [rcx+r9]
0x180004889  cmp     r8b, r15b
0x18000488c  jnz     loc_180004B29
0x180004892  lea     r8d, [rcx+1]
0x180004896  mov     [rbx+4], r8d
0x18000489a  cmp     edx, r8d
0x18000489d  jbe     loc_180004D88
0x1800048a3  movzx   ecx, byte ptr [r8+r9]
0x1800048a8  mov     r9d, 1
0x1800048ae  mov     eax, ecx
0x1800048b0  and     eax, 7Fh
0x1800048b3  inc     eax
0x1800048b5  test    cl, cl
0x1800048b7  cmovs   r9d, eax
0x1800048bb  mov     eax, [rbx+20h]
0x1800048be  cmp     eax, 32h ; '2'
0x1800048c1  jnb     loc_180004DD4
0x1800048c7  mov     ecx, [rbx+348h]
0x1800048cd  add     rax, rax
0x1800048d0  mov     [rsp+78h+arg_18], r12
0x1800048d8  lea     r12, [rbx+344h]
0x1800048df  mov     edx, [r12]
0x1800048e3  mov     [rbx+rax*8+24h], r8d
0x1800048e8  mov     eax, [rbx+20h]
0x1800048eb  add     rax, rax
0x1800048ee  mov     [rbx+rax*8+28h], r9d
0x1800048f3  mov     eax, [rbx+20h]
0x1800048f6  add     rax, rax
0x1800048f9  mov     [rbx+rax*8+2Ch], ecx
0x1800048fd  mov     rcx, rbx; this
0x180004900  mov     eax, [rbx+20h]
0x180004903  add     rax, 3
0x180004907  add     rax, rax
0x18000490a  mov     [rbx+rax*8], edx
0x18000490d  mov     rdx, r12; unsigned int *
0x180004910  inc     dword ptr [rbx+20h]
0x180004913  call    ?HrGetLength@CLdapBer@@QEAAKPEAK@Z; CLdapBer::HrGetLength(ulong *)
0x180004918  mov     ebp, eax
0x18000491a  test    eax, eax
0x18000491c  jnz     loc_180004DDE
0x180004922  mov     eax, [rbx+4]
0x180004925  mov     [rbx+348h], eax
0x18000492b  mov     r12, [rsp+78h+arg_18]
0x180004933  mov     eax, [rbx]
0x180004935  cmp     [rbx+4], eax
0x180004938  ja      loc_1800049D3
0x18000493e  test    ebp, ebp
0x180004940  jnz     loc_1800049D8
0x180004946  lea     rbp, [rdi+348h]
0x18000494d  mov     rcx, rbx; this
0x180004950  mov     rdx, rbp; unsigned __int16 *
0x180004953  call    ?HrGetValue@CLdapBer@@QEAAKPEAGKKE@Z; CLdapBer::HrGetValue(ushort *,ulong,ulong,uchar)
0x180004958  test    eax, eax
0x18000495a  jnz     loc_180004E04
0x180004960  mov     [rsp+78h+lpUsedDefaultChar], r14; lpUsedDefaultChar
0x180004965  lea     rbx, [rdi+20h]
0x180004969  mov     [rsp+78h+lpDefaultChar], r14; lpDefaultChar
0x18000496e  mov     r9d, 0FFFFFFFFh; cchWideChar
0x180004974  mov     [rsp+78h+cbMultiByte], 31Fh; cbMultiByte
0x18000497c  mov     r8, rbp; lpWideCharStr
0x18000497f  mov     edx, 400h; dwFlags
0x180004984  mov     [rsp+78h+lpMultiByteStr], rbx; lpMultiByteStr
0x180004989  xor     ecx, ecx; CodePage
0x18000498b  call    cs:__imp_WideCharToMultiByte
0x180004992  nop     dword ptr [rax+rax+00h]
0x180004997  test    eax, eax
0x180004999  jnz     loc_180004A41
0x18000499f  mov     edx, 5Ah ; 'Z'
0x1800049a4  mov     rcx, rsi
0x1800049a7  call    SetConnectionError
0x1800049ac  mov     r15, [rsp+78h+var_28]
0x1800049b1  mov     rdi, [rsp+78h+arg_10]
0x1800049b9  mov     rax, r14
0x1800049bc  mov     r14, [rsp+78h+var_20]
0x1800049c1  mov     rbp, [rsp+78h+arg_0]
0x1800049c9  add     rsp, 60h
0x1800049cd  pop     r13
0x1800049cf  pop     rsi
0x1800049d0  pop     rbx
0x1800049d1  retn
0x1800049d3  mov     ebp, 80070057h
0x1800049d8  cmp     cs:g_fTracingOn, r14d
0x1800049df  jz      loc_180004E3A
0x1800049e5  cmp     cs:g_fProviderEnabled, r14d
0x1800049ec  jz      loc_180004E3A
0x1800049f2  test    cs:g_ulTraceFlags, 400000h
0x1800049fd  jz      loc_180004E3A
0x180004a03  mov     r9d, ebp
0x180004a06  lea     rdx, aLdapnextattr2C; "ldapNextAttr 2 connection 0x%x received"...
0x180004a0d  jmp     loc_180004E2D
0x180004a12  mov     edx, 52h ; 'R'
0x180004a17  mov     rcx, rsi
0x180004a1a  call    SetConnectionError
0x180004a1f  jmp     short loc_1800049AC
0x180004a21  call    cs:__imp_TlsGetValue
0x180004a28  nop     dword ptr [rax+rax+00h]
0x180004a2d  mov     r15, rax
0x180004a30  test    rax, rax
0x180004a33  jz      loc_180004AF7
0x180004a39  mov     [r15], r14d
0x180004a3c  jmp     loc_180004802
0x180004a41  dec     eax
0x180004a43  test    r13b, r13b
0x180004a46  mov     [rax+rdi+20h], r14b
0x180004a4b  mov     r14, rbx
0x180004a4e  cmovnz  r14, rbp
0x180004a52  jmp     loc_1800049AC
0x180004a60  cmp     [rdi+10h], rsi
0x180004a64  jz      loc_1800047CD
0x180004a6a  mov     rdi, [rdi]
0x180004a6d  test    rdi, rdi
0x180004a70  jnz     short loc_180004A60
0x180004a72  jmp     loc_1800047CD
0x180004a77  mov     rcx, rbx; this
0x180004a7a  call    ?HrSkipElement@CLdapBer@@QEAAKXZ; CLdapBer::HrSkipElement(void)
0x180004a7f  test    eax, eax
0x180004a81  jnz     loc_180004CD9
0x180004a87  mov     eax, [rbx+4]
0x180004a8a  mov     r8d, [rbx]
0x180004a8d  cmp     r8d, eax
0x180004a90  jbe     short loc_180004AB3
0x180004a92  mov     ecx, eax
0x180004a94  mov     rax, [rbx+10h]
0x180004a98  movzx   r15d, byte ptr [rcx+rax]
0x180004a9d  jmp     loc_180004859
0x180004aa2  mov     edx, 54h ; 'T'
0x180004aa7  call    SetConnectionError
0x180004aac  xor     eax, eax
0x180004aae  jmp     loc_1800049C9
0x180004ab3  cmp     cs:g_fTracingOn, r14d
0x180004aba  jz      loc_1800049AC
0x180004ac0  cmp     cs:g_fProviderEnabled, r14d
0x180004ac7  jz      loc_1800049AC
0x180004acd  test    cs:g_ulTraceFlags, 2000h
0x180004ad8  jz      loc_1800049AC
0x180004ade  mov     r9d, eax
0x180004ae1  lea     rdx, aHrpeektagRanOu; "HrPeekTag ran out of data, length 0x%x,"...
0x180004ae8  mov     ecx, 2000h
0x180004aed  call    LDAPClientPrint
0x180004af2  jmp     loc_1800049AC
0x180004af7  mov     edx, 6C546864h
0x180004afc  mov     ecx, ebp
0x180004afe  call    ldapMalloc
0x180004b03  mov     r15, rax
0x180004b06  test    rax, rax
0x180004b09  jz      loc_180004802
0x180004b0f  mov     ecx, cs:GlobalTlsLastErrorIndex; dwTlsIndex
0x180004b15  mov     rdx, rax; lpTlsValue
0x180004b18  call    cs:__imp_TlsSetValue
0x180004b1f  nop     dword ptr [rax+rax+00h]
0x180004b24  jmp     loc_180004A39
0x180004b29  cmp     cs:g_fTracingOn, r14d
0x180004b30  jnz     loc_180004D76
0x180004b36  mov     ebp, 80070057h
0x180004b3b  jmp     loc_1800049D8
0x180004b40  call    GetCurrentPerThreadEntry
0x180004b45  mov     rdi, rax
0x180004b48  test    rax, rax
0x180004b4b  jnz     loc_1800047AD
0x180004b51  cmp     cs:g_fTracingOn, r14d
0x180004b58  jnz     loc_180004C56
0x180004b5e  mov     edx, 52h ; 'R'
0x180004b63  mov     rcx, rsi
0x180004b66  call    SetConnectionError
0x180004b6b  jmp     loc_1800049B1
0x180004b70  test    cs:g_ulTraceFlags, 2000h
0x180004b7b  jz      loc_1800049D8
0x180004b81  mov     r9d, ecx
0x180004b84  mov     r8d, edx
0x180004b87  lea     rdx, aHrstartreadseq_0; "HrStartReadSequence ran out of data, le"...
0x180004b8e  mov     ecx, 2000h
0x180004b93  call    LDAPClientPrint
0x180004b98  jmp     loc_1800049D8
0x180004b9d  test    cs:g_ulTraceFlags, 2000h
0x180004ba8  jz      short loc_180004B36
0x180004baa  mov     r9d, r8d
0x180004bad  lea     rdx, aHrstartreadseq; "HrStartReadSequence expected tag of 0x%"...
0x180004bb4  mov     r8d, 30h ; '0'
0x180004bba  mov     ecx, 2000h
0x180004bbf  call    LDAPClientPrint
0x180004bc4  jmp     loc_180004B36
0x180004bc9  cmp     cs:g_fTracingOn, r14d
0x180004bd0  jz      short loc_180004BFF
0x180004bd2  cmp     cs:g_fProviderEnabled, r14d
0x180004bd9  jz      short loc_180004BFF
0x180004bdb  test    cs:g_ulTraceFlags, 400000h
0x180004be6  jz      short loc_180004BFF
0x180004be8  mov     r9d, ebp
0x180004beb  lea     rdx, aLdapnextattrCo; "ldapNextAttr could not find ThreadEntry"...
0x180004bf2  mov     r8, rsi
0x180004bf5  mov     ecx, 400000h
0x180004bfa  call    LDAPClientPrint
0x180004bff  mov     ecx, ebp
0x180004c01  call    AddPerThreadEntry
0x180004c06  test    eax, eax
0x180004c08  jnz     loc_180004B40
0x180004c0e  cmp     cs:g_fTracingOn, r14d
0x180004c15  jz      short loc_180004C44
0x180004c17  cmp     cs:g_fProviderEnabled, r14d
0x180004c1e  jz      short loc_180004C44
0x180004c20  test    cs:g_ulTraceFlags, 400000h
0x180004c2b  jz      short loc_180004C44
0x180004c2d  mov     r9d, ebp
0x180004c30  lea     rdx, aLdapnextattrAd; "ldapNextAttr AddPerThreadEntry failed, "...
0x180004c37  mov     r8, rsi
0x180004c3a  mov     ecx, 400000h
0x180004c3f  call    LDAPClientPrint
0x180004c44  mov     edx, 5Ah ; 'Z'
0x180004c49  mov     rcx, rsi
0x180004c4c  call    SetConnectionError
0x180004c51  jmp     loc_1800049B1
0x180004c56  cmp     cs:g_fProviderEnabled, r14d
0x180004c5d  jz      loc_180004B5E
0x180004c63  test    cs:g_ulTraceFlags, 400000h
0x180004c6e  jz      loc_180004B5E
0x180004c74  mov     r9d, ebp
0x180004c77  lea     rdx, aLdapnextattrNo; "ldapNextAttr no per-thread entry, conne"...
0x180004c7e  mov     r8, rsi
0x180004c81  mov     ecx, 400000h
0x180004c86  call    LDAPClientPrint
0x180004c8b  jmp     loc_180004B5E
0x180004c90  cmp     cs:g_fTracingOn, r14d
0x180004c97  jz      short loc_180004CC3
0x180004c99  cmp     cs:g_fProviderEnabled, r14d
0x180004ca0  jz      short loc_180004CC3
0x180004ca2  test    cs:g_ulTraceFlags, 8000000h
  ... truncated ...
```
