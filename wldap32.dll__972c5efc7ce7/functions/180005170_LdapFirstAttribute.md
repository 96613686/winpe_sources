# LdapFirstAttribute

- ea: `0x180005170`
- end: `0x18000577e`
- name: `LdapFirstAttribute`
- size: `1550`
- prototype: `__int64 __fastcall(struct ldap_connection *)`
- caller_count: `6`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x18000461c`
- `0x1800057a0`
- `0x1800188d0`
- `0x18001b0d4`
- `0x18002cc80`
- `0x18002cea0`

## callees

- `0x180002770`
- `0x1800032d0`
- `0x180003570`
- `0x1800037a8`
- `0x180005134`
- `0x180005170`
- `0x180006510`
- `0x18001ce90`
- `0x18001e2c0`
- `0x180027530`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800051f2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800051f2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005270`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800055c8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005270`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800055c8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800051ac`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800051ac`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800051c1`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800051c1`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800053b3`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800053b3`

## string_xrefs

- `0x1800054e8`: `ldapFirstAttr could not find ThreadEntry for connection 0x%x, thread 0x%x.  Creating one.\n`
- `0x18000552c`: `ldapFirstAttr AddPerThreadEntry failed, connection 0x%x, thread 0x%x.\n`
- `0x180005575`: `ldapFirstAttr no per-thread entry, connection 0x%x, thread 0x%x.\n`
- `0x1800055b0`: `ldapFirstAttr could not allocate current attribute for thread for connection 0x%x.\n`
- `0x180005611`: `ldapFirstAttr allocated attribute at 0x%x for thread 0x%x, connection 0x%x.\n`
- `0x180005655`: `ldap_first_attribute 1 connection 0x%x received protocol error 0x%x .\n`
- `0x180005456`: `ldap_first_attribute 8 connection 0x%x received protocol error 0x%x .\n`
- `0x18000574f`: `ldap_first_attribute 2 connection 0x%x received protocol error 0x%x .\n`
- `0x180005688`: `HrStartReadSequence ran out of data, length 0x%x, offset 0x%x.\n`
- `0x1800054b4`: `HrStartReadSequence expected tag of 0x%x, received 0x%x.\n`
- `0x1800056b3`: `HrStartReadSequence 2 ran out of data, length 0x%x, offset 0x%x.\n`

## pseudocode

```c
__int64 __fastcall LdapFirstAttribute(struct ldap_connection *a1, __int64 a2, _QWORD *a3, char a4)
{
  DWORD CurrentThreadId; // r14d
  _QWORD *Value; // rax
  __int64 CurrentPerThreadEntry; // rdi
  __int64 v11; // rbx
  __int64 v12; // rax
  __int64 v13; // r14
  __int64 v14; // rdi
  unsigned int Attribute; // eax
  __int64 v16; // rdx
  unsigned int v17; // r10d
  __int64 v18; // rcx
  __int64 v19; // r8
  char v20; // cl
  unsigned int v21; // r9d
  __int64 v22; // rax
  int v23; // ecx
  int v24; // edx
  unsigned int Length; // r10d
  unsigned int v26; // eax
  int v27; // eax
  __int64 v28; // rdx
  unsigned __int8 lpMultiByteStr; // [rsp+20h] [rbp-58h]
  unsigned int v31; // [rsp+88h] [rbp+10h] BYREF
  unsigned int v32; // [rsp+90h] [rbp+18h] BYREF

  *a3 = 0;
  if ( !a2 || *(_DWORD *)(a2 + 4) != 100 )
  {
    SetConnectionError(a1, 84);
    return 0;
  }
  CurrentThreadId = GetCurrentThreadId();
  Value = TlsGetValue(GlobalTlsLastErrorIndex);
  if ( Value )
  {
    CurrentPerThreadEntry = Value[1];
    if ( CurrentPerThreadEntry )
      goto LABEL_5;
  }
  if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x400000) != 0 )
    LDAPClientPrint(
      0x400000,
      "ldapFirstAttr could not find ThreadEntry for connection 0x%x, thread 0x%x.  Creating one.\n",
      (_DWORD)a1,
      CurrentThreadId);
  if ( !(unsigned int)AddPerThreadEntry(CurrentThreadId) )
  {
    if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x400000) != 0 )
      LDAPClientPrint(
        0x400000,
        "ldapFirstAttr AddPerThreadEntry failed, connection 0x%x, thread 0x%x.\n",
        (_DWORD)a1,
        CurrentThreadId);
    SetConnectionError(a1, 90);
    return 0;
  }
  CurrentPerThreadEntry = GetCurrentPerThreadEntry();
  if ( CurrentPerThreadEntry )
  {
LABEL_5:
    EnterCriticalSection(&PerThreadListLock);
    v11 = *(_QWORD *)(CurrentPerThreadEntry + 32);
    if ( v11 )
    {
      while ( *(struct ldap_connection **)(v11 + 16) != a1 )
      {
        v11 = *(_QWORD *)v11;
        if ( !v11 )
          goto LABEL_8;
      }
LABEL_11:
      v13 = 0;
      LeaveCriticalSection(&PerThreadListLock);
      SetConnectionError(a1, 0);
      v14 = *(_QWORD *)(a2 + 8);
      if ( !v14 )
        goto LABEL_84;
      Attribute = LdapGoToFirstAttribute(a1, *(struct CLdapBer **)(a2 + 8));
      if ( Attribute )
      {
        if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x400000) != 0 )
          LDAPClientPrint(
            0x400000,
            "ldap_first_attribute 1 connection 0x%x received protocol error 0x%x .\n",
            a1,
            Attribute);
        goto LABEL_84;
      }
      v16 = *(unsigned int *)(v14 + 4);
      v17 = *(_DWORD *)v14;
      if ( *(_DWORD *)v14 <= (unsigned int)v16 )
      {
        if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x2000) != 0 )
          LDAPClientPrint(0x2000, "HrStartReadSequence ran out of data, length 0x%x, offset 0x%x.\n", v17, v16);
        Length = 16;
        goto LABEL_35;
      }
      v18 = *(_QWORD *)(v14 + 16);
      if ( *(_BYTE *)(v16 + v18) == 48 )
      {
        v19 = (unsigned int)(v16 + 1);
        *(_DWORD *)(v14 + 4) = v19;
        if ( v17 <= (unsigned int)v19 )
        {
          if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x2000) != 0 )
            LDAPClientPrint(
              0x2000,
              "HrStartReadSequence 2 ran out of data, length 0x%x, offset 0x%x.\n",
              v17,
              (unsigned int)v19);
        }
        else
        {
          v20 = *(_BYTE *)(v19 + v18);
          v21 = 1;
          if ( v20 < 0 )
            v21 = (v20 & 0x7F) + 1;
          v22 = *(unsigned int *)(v14 + 32);
          if ( (unsigned int)v22 >= 0x32 )
          {
            Length = -2147024882;
          }
          else
          {
            v23 = *(_DWORD *)(v14 + 840);
            v24 = *(_DWORD *)(v14 + 836);
            *(_DWORD *)(v14 + 16 * v22 + 36) = v19;
            *(_DWORD *)(v14 + 16LL * *(unsigned int *)(v14 + 32) + 40) = v21;
            *(_DWORD *)(v14 + 16LL * *(unsigned int *)(v14 + 32) + 44) = v23;
            *(_DWORD *)(v14 + 16 * ((unsigned int)(*(_DWORD *)(v14 + 32))++ + 3LL)) = v24;
            Length = CLdapBer::HrGetLength((CLdapBer *)v14, (unsigned int *)(v14 + 836));
            if ( Length )
              CLdapBer::HrPopSeqStack(
                (CLdapBer *)v14,
                &v32,
                &v31,
                (unsigned int *)(v14 + 840),
                (unsigned int *)(v14 + 836));
            else
              *(_DWORD *)(v14 + 840) = *(_DWORD *)(v14 + 4);
          }
          if ( *(_DWORD *)(v14 + 4) <= *(_DWORD *)v14 )
          {
            if ( !Length )
            {
              v26 = CLdapBer::HrGetValue((CLdapBer *)v14, (unsigned __int16 *)(v11 + 840), v19, v21, lpMultiByteStr);
              if ( !v26 )
              {
                v27 = WideCharToMultiByte(0, 0x400u, (LPCWCH)(v11 + 840), -1, (LPSTR)(v11 + 32), 799, 0, 0);
                if ( v27 )
                {
                  *(_BYTE *)((unsigned int)(v27 - 1) + v11 + 32) = 0;
                  v13 = v11 + 32;
                  if ( a4 )
                    v13 = v11 + 840;
                  *a3 = v14;
                  return v13;
                }
                v28 = 90;
LABEL_29:
                SetConnectionError(a1, v28);
                return v13;
              }
              if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x400000) != 0 )
                LDAPClientPrint(
                  0x400000,
                  "ldap_first_attribute 2 connection 0x%x received protocol error 0x%x .\n",
                  a1,
                  v26);
LABEL_84:
              v28 = 84;
              goto LABEL_29;
            }
LABEL_35:
            if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x400000) != 0 )
              LDAPClientPrint(
                0x400000,
                "ldap_first_attribute 8 connection 0x%x received protocol error 0x%x .\n",
                (_DWORD)a1,
                Length);
            return v13;
          }
        }
      }
      else if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x2000) != 0 )
      {
        LDAPClientPrint(
          0x2000,
          "HrStartReadSequence expected tag of 0x%x, received 0x%x.\n",
          48,
          *(unsigned __int8 *)(v16 + v18));
      }
      Length = -2147024809;
      goto LABEL_35;
    }
LABEL_8:
    v12 = ldapMalloc(2440, 1920221516);
    v11 = v12;
    if ( v12 )
    {
      if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x400000) != 0 )
        LDAPClientPrint(
          0x400000,
          "ldapFirstAttr allocated attribute at 0x%x for thread 0x%x, connection 0x%x.\n",
          v12,
          CurrentThreadId,
          (_DWORD)a1);
      *(_DWORD *)(v11 + 8) = CurrentThreadId;
      *(_DWORD *)(v11 + 24) = 1684095564;
      *(_DWORD *)(v11 + 832) = 1684095564;
      *(_QWORD *)v11 = *(_QWORD *)(CurrentPerThreadEntry + 32);
      *(_QWORD *)(v11 + 16) = a1;
      *(_QWORD *)(CurrentPerThreadEntry + 32) = v11;
      goto LABEL_11;
    }
    if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x4000) != 0 )
      LDAPClientPrint(
        0x4000,
        "ldapFirstAttr could not allocate current attribute for thread for connection 0x%x.\n",
        (_DWORD)a1);
    LeaveCriticalSection(&PerThreadListLock);
    SetConnectionError(a1, 90);
    return 0;
  }
  else
  {
    if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x400000) != 0 )
      LDAPClientPrint(
        0x400000,
        "ldapFirstAttr no per-thread entry, connection 0x%x, thread 0x%x.\n",
        (_DWORD)a1,
        CurrentThreadId);
    SetConnectionError(a1, 82);
    return 0;
  }
}

```

## disassembly

```asm
0x180005170  push    rbp
0x180005172  push    rsi
0x180005173  push    r13
0x180005175  push    r15
0x180005177  sub     rsp, 58h
0x18000517b  mov     qword ptr [r8], 0
0x180005182  movzx   r13d, r9b
0x180005186  mov     r15, r8
0x180005189  mov     rsi, rdx
0x18000518c  mov     rbp, rcx
0x18000518f  test    rdx, rdx
0x180005192  jz      loc_18000576D
0x180005198  cmp     dword ptr [rdx+4], 64h ; 'd'
0x18000519c  jnz     loc_18000576D
0x1800051a2  mov     [rsp+78h+var_38], r14
0x1800051a7  mov     [rsp+78h+var_28], rdi
0x1800051ac  call    cs:__imp_GetCurrentThreadId
0x1800051b3  nop     dword ptr [rax+rax+00h]
0x1800051b8  mov     ecx, cs:GlobalTlsLastErrorIndex; dwTlsIndex
0x1800051be  mov     r14d, eax
0x1800051c1  call    cs:__imp_TlsGetValue
0x1800051c8  nop     dword ptr [rax+rax+00h]
0x1800051cd  test    rax, rax
0x1800051d0  jz      loc_1800054C6
0x1800051d6  mov     rdi, [rax+8]
0x1800051da  test    rdi, rdi
0x1800051dd  jz      loc_1800054C6
0x1800051e3  lea     rcx, PerThreadListLock; lpCriticalSection
0x1800051ea  mov     [rsp+78h+arg_0], rbx
0x1800051f2  call    cs:__imp_EnterCriticalSection
0x1800051f9  nop     dword ptr [rax+rax+00h]
0x1800051fe  mov     rbx, [rdi+20h]
0x180005202  test    rbx, rbx
0x180005205  jz      short loc_180005215
0x180005207  cmp     [rbx+10h], rbp
0x18000520b  jz      short loc_180005261
0x18000520d  mov     rbx, [rbx]
0x180005210  test    rbx, rbx
0x180005213  jnz     short loc_180005207
0x180005215  mov     edx, 7274414Ch
0x18000521a  mov     ecx, 988h
0x18000521f  call    ldapMalloc
0x180005224  mov     rbx, rax
0x180005227  test    rax, rax
0x18000522a  jz      loc_18000558E
0x180005230  cmp     cs:g_fTracingOn, 0
0x180005237  jnz     loc_1800055E8
0x18000523d  mov     [rbx+8], r14d
0x180005241  mov     dword ptr [rbx+18h], 6461424Ch
0x180005248  mov     dword ptr [rbx+340h], 6461424Ch
0x180005252  mov     rax, [rdi+20h]
0x180005256  mov     [rbx], rax
0x180005259  mov     [rbx+10h], rbp
0x18000525d  mov     [rdi+20h], rbx
0x180005261  lea     rcx, PerThreadListLock; lpCriticalSection
0x180005268  mov     [rsp+78h+var_30], r12
0x18000526d  xor     r14d, r14d
0x180005270  call    cs:__imp_LeaveCriticalSection
0x180005277  nop     dword ptr [rax+rax+00h]
0x18000527c  xor     edx, edx
0x18000527e  mov     rcx, rbp
0x180005281  call    SetConnectionError
0x180005286  mov     rdi, [rsi+8]
0x18000528a  test    rdi, rdi
0x18000528d  jz      loc_180005763
0x180005293  mov     rdx, rdi; struct CLdapBer *
0x180005296  mov     rcx, rbp; struct ldap_connection *
0x180005299  call    ?LdapGoToFirstAttribute@@YAKPEAUldap_connection@@PEAVCLdapBer@@@Z; LdapGoToFirstAttribute(ldap_connection *,CLdapBer *)
0x18000529e  test    eax, eax
0x1800052a0  jnz     loc_180005627
0x1800052a6  mov     edx, [rdi+4]
0x1800052a9  mov     r10d, [rdi]
0x1800052ac  cmp     r10d, edx
0x1800052af  jbe     loc_180005421
0x1800052b5  mov     rcx, [rdi+10h]
0x1800052b9  movzx   r8d, byte ptr [rdx+rcx]
0x1800052be  cmp     r8b, 30h ; '0'
0x1800052c2  jnz     loc_18000540C
0x1800052c8  lea     r8d, [rdx+1]
0x1800052cc  mov     [rdi+4], r8d
0x1800052d0  cmp     r10d, r8d
0x1800052d3  jbe     loc_1800056CC
0x1800052d9  movzx   ecx, byte ptr [r8+rcx]
0x1800052de  mov     r9d, 1
0x1800052e4  mov     eax, ecx
0x1800052e6  and     eax, 7Fh
0x1800052e9  inc     eax
0x1800052eb  test    cl, cl
0x1800052ed  cmovs   r9d, eax
0x1800052f1  mov     eax, [rdi+20h]
0x1800052f4  cmp     eax, 32h ; '2'
0x1800052f7  jnb     loc_1800056F9
0x1800052fd  mov     ecx, [rdi+348h]
0x180005303  lea     r12, [rdi+344h]
0x18000530a  mov     edx, [r12]
0x18000530e  add     rax, rax
0x180005311  mov     [rdi+rax*8+24h], r8d
0x180005316  mov     eax, [rdi+20h]
0x180005319  add     rax, rax
0x18000531c  mov     [rdi+rax*8+28h], r9d
0x180005321  mov     eax, [rdi+20h]
0x180005324  add     rax, rax
0x180005327  mov     [rdi+rax*8+2Ch], ecx
0x18000532b  mov     rcx, rdi; this
0x18000532e  mov     eax, [rdi+20h]
0x180005331  add     rax, 3
0x180005335  add     rax, rax
0x180005338  mov     [rdi+rax*8], edx
0x18000533b  mov     rdx, r12; unsigned int *
0x18000533e  inc     dword ptr [rdi+20h]
0x180005341  call    ?HrGetLength@CLdapBer@@QEAAKPEAK@Z; CLdapBer::HrGetLength(ulong *)
0x180005346  mov     r10d, eax
0x180005349  test    eax, eax
0x18000534b  jnz     loc_180005704
0x180005351  mov     eax, [rdi+4]
0x180005354  mov     [rdi+348h], eax
0x18000535a  mov     eax, [rdi]
0x18000535c  cmp     [rdi+4], eax
0x18000535f  ja      loc_180005419
0x180005365  test    r10d, r10d
0x180005368  jnz     loc_180005434
0x18000536e  lea     rsi, [rbx+348h]
0x180005375  mov     rcx, rdi; this
0x180005378  mov     rdx, rsi; unsigned __int16 *
0x18000537b  call    ?HrGetValue@CLdapBer@@QEAAKPEAGKKE@Z; CLdapBer::HrGetValue(ushort *,ulong,ulong,uchar)
0x180005380  test    eax, eax
0x180005382  jnz     loc_18000572D
0x180005388  mov     [rsp+78h+lpUsedDefaultChar], r14; lpUsedDefaultChar
0x18000538d  lea     r12, [rbx+20h]
0x180005391  mov     [rsp+78h+lpDefaultChar], r14; lpDefaultChar
0x180005396  mov     r9d, 0FFFFFFFFh; cchWideChar
0x18000539c  mov     [rsp+78h+cbMultiByte], 31Fh; cbMultiByte
0x1800053a4  mov     r8, rsi; lpWideCharStr
0x1800053a7  mov     edx, 400h; dwFlags
0x1800053ac  mov     [rsp+78h+lpMultiByteStr], r12; lpMultiByteStr
0x1800053b1  xor     ecx, ecx; CodePage
0x1800053b3  call    cs:__imp_WideCharToMultiByte
0x1800053ba  nop     dword ptr [rax+rax+00h]
0x1800053bf  test    eax, eax
0x1800053c1  jz      short loc_1800053D9
0x1800053c3  dec     eax
0x1800053c5  test    r13b, r13b
0x1800053c8  mov     [rax+rbx+20h], r14b
0x1800053cd  mov     r14, r12
0x1800053d0  cmovnz  r14, rsi
0x1800053d4  mov     [r15], rdi
0x1800053d7  jmp     short loc_1800053E6
0x1800053d9  mov     edx, 5Ah ; 'Z'
0x1800053de  mov     rcx, rbp
0x1800053e1  call    SetConnectionError
0x1800053e6  mov     r12, [rsp+78h+var_30]
0x1800053eb  mov     rax, r14
0x1800053ee  mov     rbx, [rsp+78h+arg_0]
0x1800053f6  mov     rdi, [rsp+78h+var_28]
0x1800053fb  mov     r14, [rsp+78h+var_38]
0x180005400  add     rsp, 58h
0x180005404  pop     r15
0x180005406  pop     r13
0x180005408  pop     rsi
0x180005409  pop     rbp
0x18000540a  retn
0x18000540c  cmp     cs:g_fTracingOn, r14d
0x180005413  jnz     loc_18000569E
0x180005419  mov     r10d, 80070057h
0x18000541f  jmp     short loc_180005434
0x180005421  cmp     cs:g_fTracingOn, r14d
0x180005428  jnz     loc_180005664
0x18000542e  mov     r10d, 10h
0x180005434  cmp     cs:g_fTracingOn, r14d
0x18000543b  jz      short loc_1800053E6
0x18000543d  cmp     cs:g_fProviderEnabled, r14d
0x180005444  jz      short loc_1800053E6
0x180005446  test    cs:g_ulTraceFlags, 400000h
0x180005451  jz      short loc_1800053E6
0x180005453  mov     r9d, r10d
0x180005456  lea     rdx, aLdapFirstAttri_4; "ldap_first_attribute 8 connection 0x%x "...
0x18000545d  mov     r8, rbp
0x180005460  mov     ecx, 400000h
0x180005465  call    LDAPClientPrint
0x18000546a  jmp     loc_1800053E6
0x18000546f  call    GetCurrentPerThreadEntry
0x180005474  mov     rdi, rax
0x180005477  test    rax, rax
0x18000547a  jnz     loc_1800051E3
0x180005480  cmp     cs:g_fTracingOn, eax
0x180005486  jnz     loc_180005554
0x18000548c  mov     edx, 52h ; 'R'
0x180005491  mov     rcx, rbp
0x180005494  call    SetConnectionError
0x180005499  xor     eax, eax
0x18000549b  jmp     loc_1800053F6
0x1800054a0  test    cs:g_ulTraceFlags, 2000h
0x1800054ab  jz      loc_180005419
0x1800054b1  mov     r9d, r8d
0x1800054b4  lea     rdx, aHrstartreadseq; "HrStartReadSequence expected tag of 0x%"...
0x1800054bb  mov     r8d, 30h ; '0'
0x1800054c1  jmp     loc_1800056BD
0x1800054c6  cmp     cs:g_fTracingOn, 0
0x1800054cd  jz      short loc_1800054FC
0x1800054cf  cmp     cs:g_fProviderEnabled, 0
0x1800054d6  jz      short loc_1800054FC
0x1800054d8  test    cs:g_ulTraceFlags, 400000h
0x1800054e3  jz      short loc_1800054FC
0x1800054e5  mov     r9d, r14d
0x1800054e8  lea     rdx, aLdapfirstattrC_0; "ldapFirstAttr could not find ThreadEntr"...
0x1800054ef  mov     r8, rbp
0x1800054f2  mov     ecx, 400000h
0x1800054f7  call    LDAPClientPrint
0x1800054fc  mov     ecx, r14d
0x1800054ff  call    AddPerThreadEntry
0x180005504  test    eax, eax
0x180005506  jnz     loc_18000546F
0x18000550c  cmp     cs:g_fTracingOn, eax
0x180005512  jz      short loc_180005540
0x180005514  cmp     cs:g_fProviderEnabled, eax
0x18000551a  jz      short loc_180005540
0x18000551c  test    cs:g_ulTraceFlags, 400000h
0x180005527  jz      short loc_180005540
0x180005529  mov     r9d, r14d
0x18000552c  lea     rdx, aLdapfirstattrA_0; "ldapFirstAttr AddPerThreadEntry failed,"...
0x180005533  mov     r8, rbp
0x180005536  mov     ecx, 400000h
0x18000553b  call    LDAPClientPrint
0x180005540  mov     edx, 5Ah ; 'Z'
0x180005545  mov     rcx, rbp
0x180005548  call    SetConnectionError
0x18000554d  xor     eax, eax
0x18000554f  jmp     loc_1800053F6
0x180005554  cmp     cs:g_fProviderEnabled, 0
0x18000555b  jz      loc_18000548C
0x180005561  test    cs:g_ulTraceFlags, 400000h
0x18000556c  jz      loc_18000548C
0x180005572  mov     r9d, r14d
0x180005575  lea     rdx, aLdapfirstattrN; "ldapFirstAttr no per-thread entry, conn"...
0x18000557c  mov     r8, rbp
0x18000557f  mov     ecx, 400000h
0x180005584  call    LDAPClientPrint
0x180005589  jmp     loc_18000548C
0x18000558e  cmp     cs:g_fTracingOn, 0
0x180005595  jz      short loc_1800055C1
0x180005597  cmp     cs:g_fProviderEnabled, 0
0x18000559e  jz      short loc_1800055C1
0x1800055a0  test    cs:g_ulTraceFlags, 4000h
0x1800055ab  jz      short loc_1800055C1
0x1800055ad  mov     r8, rbp
0x1800055b0  lea     rdx, aLdapfirstattrC; "ldapFirstAttr could not allocate curren"...
0x1800055b7  mov     ecx, 4000h
0x1800055bc  call    LDAPClientPrint
0x1800055c1  lea     rcx, PerThreadListLock; lpCriticalSection
0x1800055c8  call    cs:__imp_LeaveCriticalSection
0x1800055cf  nop     dword ptr [rax+rax+00h]
0x1800055d4  mov     edx, 5Ah ; 'Z'
0x1800055d9  mov     rcx, rbp
0x1800055dc  call    SetConnectionError
0x1800055e1  xor     eax, eax
0x1800055e3  jmp     loc_1800053EE
0x1800055e8  cmp     cs:g_fProviderEnabled, 0
0x1800055ef  jz      loc_18000523D
0x1800055f5  test    cs:g_ulTraceFlags, 400000h
0x180005600  jz      loc_18000523D
0x180005606  mov     r9d, r14d
0x180005609  mov     [rsp+78h+lpMultiByteStr], rbp
0x18000560e  mov     r8, rbx
0x180005611  lea     rdx, aLdapfirstattrA; "ldapFirstAttr allocated attribute at 0x"...
0x180005618  mov     ecx, 400000h
0x18000561d  call    LDAPClientPrint
0x180005622  jmp     loc_18000523D
0x180005627  cmp     cs:g_fTracingOn, r14d
0x18000562e  jz      loc_180005763
0x180005634  cmp     cs:g_fProviderEnabled, r14d
0x18000563b  jz      loc_180005763
0x180005641  test    cs:g_ulTraceFlags, 400000h
0x18000564c  jz      loc_180005763
0x180005652  mov     r9d, eax
0x180005655  lea     rdx, aLdapFirstAttri_2; "ldap_first_attribute 1 connection 0x%x "...
0x18000565c  mov     r8, rbp
0x18000565f  jmp     loc_180005759
0x180005664  cmp     cs:g_fProviderEnabled, r14d
0x18000566b  jz      loc_18000542E
0x180005671  test    cs:g_ulTraceFlags, 2000h
0x18000567c  jz      loc_18000542E
0x180005682  mov     r9d, edx
0x180005685  mov     r8d, r10d
0x180005688  lea     rdx, aHrstartreadseq_0; "HrStartReadSequence ran out of data, le"...
0x18000568f  mov     ecx, 2000h
0x180005694  call    LDAPClientPrint
0x180005699  jmp     loc_18000542E
0x18000569e  cmp     cs:g_fProviderEnabled, r14d
0x1800056a5  jz      loc_180005419
0x1800056ab  jmp     loc_1800054A0
0x1800056b0  mov     r9d, r8d
0x1800056b3  lea     rdx, aHrstartreadseq_1; "HrStartReadSequence 2 ran out of data, "...
0x1800056ba  mov     r8d, r10d
0x1800056bd  mov     ecx, 2000h
0x1800056c2  call    LDAPClientPrint
0x1800056c7  jmp     loc_180005419
0x1800056cc  cmp     cs:g_fTracingOn, r14d
0x1800056d3  jz      loc_180005419
0x1800056d9  cmp     cs:g_fProviderEnabled, r14d
0x1800056e0  jz      loc_180005419
  ... truncated ...
```
