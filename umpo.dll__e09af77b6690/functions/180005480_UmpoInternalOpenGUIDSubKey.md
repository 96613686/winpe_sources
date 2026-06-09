# UmpoInternalOpenGUIDSubKey

- ea: `0x180005480`
- end: `0x1800058be`
- name: `UmpoInternalOpenGUIDSubKey`
- size: `1086`
- prototype: `__int64 __fastcall(HKEY hKey, UUID *Uuid2, PHKEY phkResult, REGSAM samDesired, char, int *)`
- caller_count: `11`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800051e0`
- `0x180005cb4`
- `0x1800061d0`
- `0x18000681c`
- `0x180007790`
- `0x18000a030`
- `0x18000b9b8`
- `0x18000cb4c`
- `0x1800128e4`
- `0x180012a7c`
- `0x180013808`

## callees

- `0x180005480`
- `0x18000f3dc`
- `0x180010070`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000587a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005895`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000587a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005895`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800054e3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800057f5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800054e3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800057f5`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000579c`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000579c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800057bf`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800057bf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000583e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000583e`
- `RPCRT4!UuidEqual` at `0x180005504`
- `RPCRT4!UuidEqual` at `0x180005504`

## pseudocode

```c
__int64 __fastcall UmpoInternalOpenGUIDSubKey(
        HKEY hKey,
        UUID *Uuid2,
        PHKEY phkResult,
        REGSAM samDesired,
        char a5,
        int *a6)
{
  int v10; // ebx
  unsigned int *v11; // rsi
  __int64 v12; // rcx
  __int64 v13; // rcx
  __int64 v14; // rcx
  unsigned __int64 Data1_low; // rax
  __int64 v16; // rcx
  __int64 v17; // rcx
  __int64 v18; // rcx
  __int64 v19; // rcx
  __int64 v20; // rcx
  __int64 v21; // rcx
  __int64 v22; // rcx
  __int64 v23; // rcx
  LSTATUS Key; // eax
  unsigned int v25; // r14d
  __int64 v26; // rbx
  __int64 v27; // rax
  HKEY v28; // rcx
  int v30; // [rsp+50h] [rbp-69h]
  RPC_STATUS Status[3]; // [rsp+54h] [rbp-65h] BYREF
  WCHAR SubKey[8]; // [rsp+60h] [rbp-59h] BYREF
  __int16 v33; // [rsp+70h] [rbp-49h]
  wchar_t v34; // [rsp+72h] [rbp-47h]
  wchar_t v35; // [rsp+74h] [rbp-45h]
  wchar_t v36; // [rsp+76h] [rbp-43h]
  wchar_t v37; // [rsp+78h] [rbp-41h]
  __int16 v38; // [rsp+7Ah] [rbp-3Fh]
  wchar_t v39; // [rsp+7Ch] [rbp-3Dh]
  wchar_t v40; // [rsp+7Eh] [rbp-3Bh]
  wchar_t v41; // [rsp+80h] [rbp-39h]
  wchar_t v42; // [rsp+82h] [rbp-37h]
  __int16 v43; // [rsp+84h] [rbp-35h]
  wchar_t v44; // [rsp+86h] [rbp-33h]
  wchar_t v45; // [rsp+88h] [rbp-31h]
  wchar_t v46; // [rsp+8Ah] [rbp-2Fh]
  wchar_t v47; // [rsp+8Ch] [rbp-2Dh]
  __int16 v48; // [rsp+8Eh] [rbp-2Bh]
  wchar_t v49; // [rsp+90h] [rbp-29h]
  wchar_t v50; // [rsp+92h] [rbp-27h]
  wchar_t v51; // [rsp+94h] [rbp-25h]
  wchar_t v52; // [rsp+96h] [rbp-23h]
  wchar_t v53; // [rsp+98h] [rbp-21h]
  wchar_t v54; // [rsp+9Ah] [rbp-1Fh]
  wchar_t v55; // [rsp+9Ch] [rbp-1Dh]
  wchar_t v56; // [rsp+9Eh] [rbp-1Bh]
  wchar_t v57; // [rsp+A0h] [rbp-19h]
  wchar_t v58; // [rsp+A2h] [rbp-17h]
  wchar_t v59; // [rsp+A4h] [rbp-15h]
  wchar_t v60; // [rsp+A6h] [rbp-13h]
  __int16 v61; // [rsp+A8h] [rbp-11h]

  Status[0] = 0;
  v30 = 0;
  *phkResult = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  if ( samDesired != 131097 || !a6 )
  {
LABEL_9:
    _mm_lfence();
    v12 = HIBYTE(Uuid2->Data1) & 0xF;
    SubKey[0] = a0123456789abcd[(unsigned __int64)HIBYTE(Uuid2->Data1) >> 4];
    SubKey[1] = a0123456789abcd[v12];
    _mm_lfence();
    v13 = BYTE2(Uuid2->Data1) & 0xF;
    SubKey[2] = a0123456789abcd[(unsigned __int64)BYTE2(Uuid2->Data1) >> 4];
    SubKey[3] = a0123456789abcd[v13];
    _mm_lfence();
    v14 = BYTE1(Uuid2->Data1) & 0xF;
    SubKey[4] = a0123456789abcd[(unsigned __int64)BYTE1(Uuid2->Data1) >> 4];
    SubKey[5] = a0123456789abcd[v14];
    _mm_lfence();
    LOBYTE(v14) = Uuid2->Data1;
    Data1_low = LOBYTE(Uuid2->Data1);
    v33 = 45;
    SubKey[6] = a0123456789abcd[Data1_low >> 4];
    SubKey[7] = a0123456789abcd[v14 & 0xF];
    _mm_lfence();
    v16 = HIBYTE(Uuid2->Data2) & 0xF;
    v34 = a0123456789abcd[(unsigned __int64)HIBYTE(Uuid2->Data2) >> 4];
    v35 = a0123456789abcd[v16];
    _mm_lfence();
    LOBYTE(v16) = Uuid2->Data2;
    v38 = v33;
    v36 = a0123456789abcd[(unsigned __int64)(unsigned __int8)v16 >> 4];
    v37 = a0123456789abcd[v16 & 0xF];
    _mm_lfence();
    v17 = HIBYTE(Uuid2->Data3) & 0xF;
    v39 = a0123456789abcd[(unsigned __int64)HIBYTE(Uuid2->Data3) >> 4];
    v40 = a0123456789abcd[v17];
    _mm_lfence();
    LOBYTE(v17) = Uuid2->Data3;
    v43 = v33;
    v41 = a0123456789abcd[(unsigned __int64)(unsigned __int8)v17 >> 4];
    v42 = a0123456789abcd[v17 & 0xF];
    _mm_lfence();
    v18 = Uuid2->Data4[0] & 0xF;
    v44 = a0123456789abcd[(unsigned __int64)Uuid2->Data4[0] >> 4];
    v45 = a0123456789abcd[v18];
    _mm_lfence();
    LOBYTE(v18) = Uuid2->Data4[1];
    v48 = v33;
    v46 = a0123456789abcd[(unsigned __int64)(unsigned __int8)v18 >> 4];
    v47 = a0123456789abcd[v18 & 0xF];
    _mm_lfence();
    v19 = Uuid2->Data4[2] & 0xF;
    v49 = a0123456789abcd[(unsigned __int64)Uuid2->Data4[2] >> 4];
    v50 = a0123456789abcd[v19];
    _mm_lfence();
    v20 = Uuid2->Data4[3] & 0xF;
    v51 = a0123456789abcd[(unsigned __int64)Uuid2->Data4[3] >> 4];
    v52 = a0123456789abcd[v20];
    _mm_lfence();
    v21 = Uuid2->Data4[4] & 0xF;
    v53 = a0123456789abcd[(unsigned __int64)Uuid2->Data4[4] >> 4];
    v54 = a0123456789abcd[v21];
    _mm_lfence();
    v22 = Uuid2->Data4[5] & 0xF;
    v55 = a0123456789abcd[(unsigned __int64)Uuid2->Data4[5] >> 4];
    v56 = a0123456789abcd[v22];
    _mm_lfence();
    v23 = Uuid2->Data4[6] & 0xF;
    v57 = a0123456789abcd[(unsigned __int64)Uuid2->Data4[6] >> 4];
    v58 = a0123456789abcd[v23];
    _mm_lfence();
    LOBYTE(v23) = Uuid2->Data4[7];
    v61 = 0;
    v59 = a0123456789abcd[(unsigned __int64)(unsigned __int8)v23 >> 4];
    v60 = a0123456789abcd[v23 & 0xF];
    if ( a5 )
      Key = RegOpenKeyExW(hKey, SubKey, 0, samDesired, phkResult);
    else
      Key = RegCreateKeyExW(hKey, SubKey, 0, 0, 0, samDesired, 0, phkResult, 0);
    v25 = Key;
    if ( Key || samDesired != 131097 || !a6 )
      goto LABEL_29;
    if ( *((_BYTE *)a6 + 112) != 1 )
      MicrosoftTelemetryAssertTriggeredNoArgs();
    EnterCriticalSection((LPCRITICAL_SECTION)(a6 + 18));
    v26 = (__int64)&a6[8 * *a6 + 2];
    if ( *(_DWORD *)(v26 + 24) )
    {
      v27 = 0;
      if ( a6[8] )
      {
        v27 = 1;
        if ( a6[16] )
        {
LABEL_26:
          *a6 = ((unsigned __int8)*a6 - 1) & 1;
          if ( *((_BYTE *)a6 + 112) != 1 )
            MicrosoftTelemetryAssertTriggeredNoArgs();
          LeaveCriticalSection((LPCRITICAL_SECTION)(a6 + 18));
LABEL_29:
          if ( !v30 )
            return v25;
          goto LABEL_30;
        }
      }
      v26 = (__int64)&a6[8 * v27 + 2];
    }
    if ( v26 )
    {
      v28 = *(HKEY *)(v26 + 16);
      if ( (unsigned __int64)v28 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
      {
        RegCloseKey(v28);
        *(_QWORD *)(v26 + 16) = -1;
      }
      *(UUID *)v26 = *Uuid2;
      *(_QWORD *)(v26 + 16) = *phkResult;
      *(_DWORD *)(v26 + 24) = 1;
    }
    goto LABEL_26;
  }
  if ( *((_BYTE *)a6 + 112) != 1 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  EnterCriticalSection((LPCRITICAL_SECTION)(a6 + 18));
  v10 = 0;
  while ( 1 )
  {
    v11 = (unsigned int *)&a6[8 * v10];
    if ( UuidEqual((UUID *)(v11 + 2), Uuid2, Status) )
      break;
    if ( (unsigned int)++v10 >= 2 )
    {
      v30 = 1;
      goto LABEL_9;
    }
  }
  v25 = 0;
  *phkResult = (HKEY)*((_QWORD *)v11 + 3);
  ++v11[8];
LABEL_30:
  if ( *((_BYTE *)a6 + 112) != 1 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  LeaveCriticalSection((LPCRITICAL_SECTION)(a6 + 18));
  return v25;
}

```

## disassembly

```asm
0x180005480  push    rbp
0x180005482  push    rbx
0x180005483  push    rsi
0x180005484  push    rdi
0x180005485  push    r12
0x180005487  push    r13
0x180005489  push    r14
0x18000548b  push    r15
0x18000548d  lea     rbp, [rsp-0Fh]
0x180005492  sub     rsp, 0C8h
0x180005499  mov     rax, cs:__security_cookie
0x1800054a0  xor     rax, rsp
0x1800054a3  mov     [rbp+47h+var_50], rax
0x1800054a7  mov     rdi, [rbp+47h+arg_28]
0x1800054ab  xor     esi, esi
0x1800054ad  mov     [rbp+47h+Status], esi
0x1800054b0  mov     r13d, r9d
0x1800054b3  mov     [rbp+47h+var_B0], esi
0x1800054b6  mov     r12, r8
0x1800054b9  mov     qword ptr [r8], 0FFFFFFFFFFFFFFFFh
0x1800054c0  mov     r15, rdx
0x1800054c3  mov     r14, rcx
0x1800054c6  cmp     r9d, 20019h
0x1800054cd  jnz     short loc_180005522
0x1800054cf  test    rdi, rdi
0x1800054d2  jz      short loc_180005522
0x1800054d4  cmp     byte ptr [rdi+70h], 1
0x1800054d8  jz      short loc_1800054DF
0x1800054da  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800054df  lea     rcx, [rdi+48h]; lpCriticalSection
0x1800054e3  call    cs:__imp_EnterCriticalSection
0x1800054e9  mov     ebx, esi
0x1800054eb  nop     dword ptr [rax+rax+00h]
0x1800054f0  mov     esi, ebx
0x1800054f2  lea     r8, [rbp+47h+Status]; Status
0x1800054f6  shl     rsi, 5
0x1800054fa  mov     rdx, r15; Uuid2
0x1800054fd  add     rsi, rdi
0x180005500  lea     rcx, [rsi+8]; Uuid1
0x180005504  call    cs:__imp_UuidEqual
0x18000550a  test    eax, eax
0x18000550c  jnz     loc_1800057A4
0x180005512  inc     ebx
0x180005514  cmp     ebx, 2
0x180005517  jb      short loc_1800054F0
0x180005519  mov     [rbp+47h+var_B0], 1
0x180005520  xor     esi, esi
0x180005522  lfence
0x180005525  movzx   ecx, byte ptr [r15+3]
0x18000552a  lea     r8, a0123456789abcd; "0123456789ABCDEF"
0x180005531  mov     eax, ecx
0x180005533  shr     rax, 4
0x180005537  and     ecx, 0Fh
0x18000553a  movzx   eax, word ptr [r8+rax*2]
0x18000553f  mov     [rbp+47h+SubKey], ax
0x180005543  movzx   eax, word ptr [r8+rcx*2]
0x180005548  mov     [rbp+47h+var_9E], ax
0x18000554c  lfence
0x18000554f  movzx   ecx, byte ptr [r15+2]
0x180005554  mov     eax, ecx
0x180005556  shr     rax, 4
0x18000555a  and     ecx, 0Fh
0x18000555d  movzx   eax, word ptr [r8+rax*2]
0x180005562  mov     [rbp+47h+var_9C], ax
0x180005566  movzx   eax, word ptr [r8+rcx*2]
0x18000556b  mov     [rbp+47h+var_9A], ax
0x18000556f  lfence
0x180005572  movzx   ecx, byte ptr [r15+1]
0x180005577  mov     eax, ecx
0x180005579  shr     rax, 4
0x18000557d  and     ecx, 0Fh
0x180005580  movzx   eax, word ptr [r8+rax*2]
0x180005585  mov     [rbp+47h+var_98], ax
0x180005589  movzx   eax, word ptr [r8+rcx*2]
0x18000558e  mov     [rbp+47h+var_96], ax
0x180005592  lfence
0x180005595  movzx   ecx, byte ptr [r15]
0x180005599  mov     edx, 2Dh ; '-'
0x18000559e  mov     eax, ecx
0x1800055a0  mov     [rbp+47h+var_90], dx
0x1800055a4  shr     rax, 4
0x1800055a8  and     ecx, 0Fh
0x1800055ab  movzx   eax, word ptr [r8+rax*2]
0x1800055b0  mov     [rbp+47h+var_94], ax
0x1800055b4  movzx   eax, word ptr [r8+rcx*2]
0x1800055b9  mov     [rbp+47h+var_92], ax
0x1800055bd  lfence
0x1800055c0  movzx   ecx, byte ptr [r15+5]
0x1800055c5  mov     eax, ecx
0x1800055c7  shr     rax, 4
0x1800055cb  and     ecx, 0Fh
0x1800055ce  movzx   eax, word ptr [r8+rax*2]
0x1800055d3  mov     [rbp+47h+var_8E], ax
0x1800055d7  movzx   eax, word ptr [r8+rcx*2]
0x1800055dc  mov     [rbp+47h+var_8C], ax
0x1800055e0  lfence
0x1800055e3  movzx   ecx, byte ptr [r15+4]
0x1800055e8  mov     eax, ecx
0x1800055ea  mov     [rbp+47h+var_86], dx
0x1800055ee  shr     rax, 4
0x1800055f2  and     ecx, 0Fh
0x1800055f5  movzx   eax, word ptr [r8+rax*2]
0x1800055fa  mov     [rbp+47h+var_8A], ax
0x1800055fe  movzx   eax, word ptr [r8+rcx*2]
0x180005603  mov     [rbp+47h+var_88], ax
0x180005607  lfence
0x18000560a  movzx   ecx, byte ptr [r15+7]
0x18000560f  mov     eax, ecx
0x180005611  shr     rax, 4
0x180005615  and     ecx, 0Fh
0x180005618  movzx   eax, word ptr [r8+rax*2]
0x18000561d  mov     [rbp+47h+var_84], ax
0x180005621  movzx   eax, word ptr [r8+rcx*2]
0x180005626  mov     [rbp+47h+var_82], ax
0x18000562a  lfence
0x18000562d  movzx   ecx, byte ptr [r15+6]
0x180005632  mov     eax, ecx
0x180005634  mov     [rbp+47h+var_7C], dx
0x180005638  shr     rax, 4
0x18000563c  and     ecx, 0Fh
0x18000563f  movzx   eax, word ptr [r8+rax*2]
0x180005644  mov     [rbp+47h+var_80], ax
0x180005648  movzx   eax, word ptr [r8+rcx*2]
0x18000564d  mov     [rbp+47h+var_7E], ax
0x180005651  lfence
0x180005654  movzx   ecx, byte ptr [r15+8]
0x180005659  mov     eax, ecx
0x18000565b  shr     rax, 4
0x18000565f  and     ecx, 0Fh
0x180005662  movzx   eax, word ptr [r8+rax*2]
0x180005667  mov     [rbp+47h+var_7A], ax
0x18000566b  movzx   eax, word ptr [r8+rcx*2]
0x180005670  mov     [rbp+47h+var_78], ax
0x180005674  lfence
0x180005677  movzx   ecx, byte ptr [r15+9]
0x18000567c  mov     eax, ecx
0x18000567e  mov     [rbp+47h+var_72], dx
0x180005682  shr     rax, 4
0x180005686  and     ecx, 0Fh
0x180005689  movzx   eax, word ptr [r8+rax*2]
0x18000568e  mov     [rbp+47h+var_76], ax
0x180005692  movzx   eax, word ptr [r8+rcx*2]
0x180005697  mov     [rbp+47h+var_74], ax
0x18000569b  lfence
0x18000569e  movzx   ecx, byte ptr [r15+0Ah]
0x1800056a3  mov     eax, ecx
0x1800056a5  shr     rax, 4
0x1800056a9  and     ecx, 0Fh
0x1800056ac  movzx   eax, word ptr [r8+rax*2]
0x1800056b1  mov     [rbp+47h+var_70], ax
0x1800056b5  movzx   eax, word ptr [r8+rcx*2]
0x1800056ba  mov     [rbp+47h+var_6E], ax
0x1800056be  lfence
0x1800056c1  movzx   ecx, byte ptr [r15+0Bh]
0x1800056c6  mov     eax, ecx
0x1800056c8  shr     rax, 4
0x1800056cc  and     ecx, 0Fh
0x1800056cf  movzx   eax, word ptr [r8+rax*2]
0x1800056d4  mov     [rbp+47h+var_6C], ax
0x1800056d8  movzx   eax, word ptr [r8+rcx*2]
0x1800056dd  mov     [rbp+47h+var_6A], ax
0x1800056e1  lfence
0x1800056e4  movzx   ecx, byte ptr [r15+0Ch]
0x1800056e9  mov     eax, ecx
0x1800056eb  shr     rax, 4
0x1800056ef  and     ecx, 0Fh
0x1800056f2  movzx   eax, word ptr [r8+rax*2]
0x1800056f7  mov     [rbp+47h+var_68], ax
0x1800056fb  movzx   eax, word ptr [r8+rcx*2]
0x180005700  mov     [rbp+47h+var_66], ax
0x180005704  lfence
0x180005707  movzx   ecx, byte ptr [r15+0Dh]
0x18000570c  mov     eax, ecx
0x18000570e  shr     rax, 4
0x180005712  and     ecx, 0Fh
0x180005715  movzx   eax, word ptr [r8+rax*2]
0x18000571a  mov     [rbp+47h+var_64], ax
0x18000571e  movzx   eax, word ptr [r8+rcx*2]
0x180005723  mov     [rbp+47h+var_62], ax
0x180005727  lfence
0x18000572a  movzx   ecx, byte ptr [r15+0Eh]
0x18000572f  mov     eax, ecx
0x180005731  shr     rax, 4
0x180005735  and     ecx, 0Fh
0x180005738  movzx   eax, word ptr [r8+rax*2]
0x18000573d  mov     [rbp+47h+var_60], ax
0x180005741  movzx   eax, word ptr [r8+rcx*2]
0x180005746  mov     [rbp+47h+var_5E], ax
0x18000574a  lfence
0x18000574d  movzx   ecx, byte ptr [r15+0Fh]
0x180005752  lea     rdx, [rbp+47h+SubKey]; lpSubKey
0x180005756  mov     eax, ecx
0x180005758  mov     [rbp+47h+var_58], si
0x18000575c  shr     rax, 4
0x180005760  and     ecx, 0Fh
0x180005763  movzx   eax, word ptr [r8+rax*2]
0x180005768  mov     [rbp+47h+var_5C], ax
0x18000576c  movzx   eax, word ptr [r8+rcx*2]
0x180005771  xor     r8d, r8d; ulOptions
0x180005774  mov     rcx, r14; hKey
0x180005777  mov     [rbp+47h+var_5A], ax
0x18000577b  cmp     [rbp+47h+arg_20], r8b
0x18000577f  jnz     short loc_1800057B7
0x180005781  mov     [rsp+100h+lpdwDisposition], rsi; lpdwDisposition
0x180005786  xor     r9d, r9d; lpClass
0x180005789  mov     [rsp+100h+phkResult], r12; phkResult
0x18000578e  mov     [rsp+100h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x180005793  mov     [rsp+100h+samDesired], r13d; samDesired
0x180005798  mov     [rsp+100h+dwOptions], esi; dwOptions
0x18000579c  call    cs:__imp_RegCreateKeyExW
0x1800057a2  jmp     short loc_1800057C5
0x1800057a4  mov     rax, [rsi+18h]
0x1800057a8  xor     r14d, r14d
0x1800057ab  mov     [r12], rax
0x1800057af  inc     dword ptr [rsi+20h]
0x1800057b2  jmp     loc_180005886
0x1800057b7  mov     r9d, r13d; samDesired
0x1800057ba  mov     qword ptr [rsp+100h+dwOptions], r12; phkResult
0x1800057bf  call    cs:__imp_RegOpenKeyExW
0x1800057c5  mov     r14d, eax
0x1800057c8  test    eax, eax
0x1800057ca  jnz     loc_180005880
0x1800057d0  cmp     r13d, 20019h
0x1800057d7  jnz     loc_180005880
0x1800057dd  test    rdi, rdi
0x1800057e0  jz      loc_180005880
0x1800057e6  cmp     byte ptr [rdi+70h], 1
0x1800057ea  jz      short loc_1800057F1
0x1800057ec  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800057f1  lea     rcx, [rdi+48h]; lpCriticalSection
0x1800057f5  call    cs:__imp_EnterCriticalSection
0x1800057fb  mov     ebx, [rdi]
0x1800057fd  shl     rbx, 5
0x180005801  add     rbx, 8
0x180005805  add     rbx, rdi
0x180005808  cmp     dword ptr [rbx+18h], 0
0x18000580c  jz      short loc_18000582B
0x18000580e  xor     eax, eax
0x180005810  cmp     [rdi+20h], eax
0x180005813  jz      short loc_180005820
0x180005815  cmp     dword ptr [rdi+40h], 0
0x180005819  mov     eax, 1
0x18000581e  jnz     short loc_180005862
0x180005820  shl     rax, 5
0x180005824  lea     rbx, [rdi+8]
0x180005828  add     rbx, rax
0x18000582b  test    rbx, rbx
0x18000582e  jz      short loc_180005862
0x180005830  mov     rcx, [rbx+10h]; hKey
0x180005834  lea     rax, [rcx-1]
0x180005838  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000583c  ja      short loc_18000584C
0x18000583e  call    cs:__imp_RegCloseKey
0x180005844  mov     qword ptr [rbx+10h], 0FFFFFFFFFFFFFFFFh
0x18000584c  movups  xmm0, xmmword ptr [r15]
0x180005850  movups  xmmword ptr [rbx], xmm0
0x180005853  mov     rax, [r12]
0x180005857  mov     [rbx+10h], rax
0x18000585b  mov     dword ptr [rbx+18h], 1
0x180005862  mov     eax, [rdi]
0x180005864  dec     eax
0x180005866  and     eax, 1
0x180005869  mov     [rdi], eax
0x18000586b  cmp     byte ptr [rdi+70h], 1
0x18000586f  jz      short loc_180005876
0x180005871  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180005876  lea     rcx, [rdi+48h]; lpCriticalSection
0x18000587a  call    cs:__imp_LeaveCriticalSection
0x180005880  cmp     [rbp+47h+var_B0], 0
0x180005884  jz      short loc_18000589B
0x180005886  cmp     byte ptr [rdi+70h], 1
0x18000588a  jz      short loc_180005891
0x18000588c  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180005891  lea     rcx, [rdi+48h]; lpCriticalSection
0x180005895  call    cs:__imp_LeaveCriticalSection
0x18000589b  mov     eax, r14d
0x18000589e  mov     rcx, [rbp+47h+var_50]
0x1800058a2  xor     rcx, rsp; StackCookie
0x1800058a5  call    __security_check_cookie
0x1800058aa  add     rsp, 0C8h
0x1800058b1  pop     r15
0x1800058b3  pop     r14
0x1800058b5  pop     r13
0x1800058b7  pop     r12
0x1800058b9  pop     rdi
0x1800058ba  pop     rsi
0x1800058bb  pop     rbx
0x1800058bc  pop     rbp
0x1800058bd  retn
```
