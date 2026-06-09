# LocalConvertStringSDToSD_Rev1

- ea: `0x180005d00`
- end: `0x18000653a`
- name: `LocalConvertStringSDToSD_Rev1`
- size: `2106`
- prototype: `__int64 __usercall@<rax>(__int64@<rcx>, __int64@<rdx>, __int64, __int64)`
- caller_count: `3`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180010b40`
- `0x180021820`
- `0x1800218d0`

## callees

- `0x180004f20`
- `0x180005730`
- `0x180005d00`
- `0x180006680`
- `0x180007fcc`
- `0x180008220`
- `0x18004f902`

## import_xrefs

- `api-ms-win-core-crt-l1-1-0!_wcsnicmp` at `0x1800062ac`
- `api-ms-win-core-crt-l1-1-0!_wcsnicmp` at `0x180006316`
- `api-ms-win-core-crt-l1-1-0!_wcsnicmp` at `0x1800062ac`
- `api-ms-win-core-crt-l1-1-0!_wcsnicmp` at `0x180006316`
- `ntdll!RtlNtStatusToDosError` at `0x18000615f`
- `ntdll!RtlNtStatusToDosError` at `0x1800061ce`
- `ntdll!RtlNtStatusToDosError` at `0x180006281`
- `ntdll!RtlNtStatusToDosError` at `0x1800062f5`
- `ntdll!RtlNtStatusToDosError` at `0x1800063d0`
- `ntdll!RtlNtStatusToDosError` at `0x1800063e7`
- `ntdll!RtlNtStatusToDosError` at `0x1800064d3`
- `ntdll!RtlNtStatusToDosError` at `0x18000615f`
- `ntdll!RtlNtStatusToDosError` at `0x1800061ce`
- `ntdll!RtlNtStatusToDosError` at `0x180006281`
- `ntdll!RtlNtStatusToDosError` at `0x1800062f5`
- `ntdll!RtlNtStatusToDosError` at `0x1800063d0`
- `ntdll!RtlNtStatusToDosError` at `0x1800063e7`
- `ntdll!RtlNtStatusToDosError` at `0x1800064d3`
- `ntdll!RtlSetSaclSecurityDescriptor` at `0x18000641a`
- `ntdll!RtlSetSaclSecurityDescriptor` at `0x18000641a`
- `ntdll!RtlSetOwnerSecurityDescriptor` at `0x1800063bb`
- `ntdll!RtlSetOwnerSecurityDescriptor` at `0x1800063bb`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x180006271`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x180006271`
- `ntdll!RtlAbsoluteToSelfRelativeSD` at `0x18000620a`
- `ntdll!RtlAbsoluteToSelfRelativeSD` at `0x18000623e`
- `ntdll!RtlAbsoluteToSelfRelativeSD` at `0x18000620a`
- `ntdll!RtlAbsoluteToSelfRelativeSD` at `0x18000623e`
- `ntdll!RtlSetGroupSecurityDescriptor` at `0x180006434`
- `ntdll!RtlSetGroupSecurityDescriptor` at `0x180006434`
- `ntdll!RtlCreateSecurityDescriptor` at `0x180005e6e`
- `ntdll!RtlCreateSecurityDescriptor` at `0x180005e6e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000612c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006167`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000612c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006167`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000616d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800061b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000616d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800061b3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006525`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006525`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006455`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006455`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000621f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180006470`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000621f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180006470`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005eb0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005eba`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800063f2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800064a8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800064ed`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800064fb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006509`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005eb0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005eba`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800063f2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800064a8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800064ed`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800064fb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006509`

## pseudocode

```c
__int64 __fastcall LocalConvertStringSDToSD_Rev1(_BYTE *a1, _BYTE *a2, char a3, wchar_t *a4, HLOCAL *a5, ULONG *a6)
{
  void *v6; // rsi
  void *v7; // r14
  wchar_t *v8; // rbx
  DWORD LastError; // edi
  HLOCAL v12; // rcx
  __int16 v13; // r15
  wchar_t v14; // ax
  wchar_t *v15; // r14
  wchar_t *v16; // r14
  int v17; // eax
  wchar_t *v19; // rbx
  __int64 *v20; // rax
  char v21; // al
  wchar_t *v22; // rbx
  __int64 *v23; // rax
  char v24; // al
  __int64 i; // rbx
  __int64 v26; // rdi
  DWORD AclForString; // eax
  __int64 j; // rbx
  __int64 v29; // rdi
  NTSTATUS v30; // eax
  DWORD v31; // eax
  HLOCAL v32; // rax
  int v33; // eax
  int v34; // eax
  int v35; // ecx
  __int64 v36; // rax
  DWORD v37; // eax
  int v38; // eax
  int v39; // eax
  int v40; // eax
  HLOCAL v41; // rax
  HLOCAL v42; // rcx
  char v43; // [rsp+40h] [rbp-69h]
  BOOLEAN v44; // [rsp+41h] [rbp-68h]
  BOOLEAN v45; // [rsp+42h] [rbp-67h]
  wchar_t *v46; // [rsp+48h] [rbp-61h] BYREF
  HLOCAL v47; // [rsp+50h] [rbp-59h]
  int v48; // [rsp+58h] [rbp-51h]
  ULONG BufferLength; // [rsp+5Ch] [rbp-4Dh] BYREF
  HLOCAL v50; // [rsp+60h] [rbp-49h]
  void *v51; // [rsp+68h] [rbp-41h] BYREF
  __int64 v52; // [rsp+70h] [rbp-39h] BYREF
  HLOCAL hMem; // [rsp+78h] [rbp-31h] BYREF
  HLOCAL v54; // [rsp+80h] [rbp-29h] BYREF
  __int64 v55; // [rsp+88h] [rbp-21h] BYREF
  _OWORD SecurityDescriptor[2]; // [rsp+90h] [rbp-19h] BYREF
  __int64 v57; // [rsp+B0h] [rbp+7h]
  char v59; // [rsp+118h] [rbp+6Fh]

  v6 = 0;
  v7 = 0;
  v52 = 0;
  v47 = 0;
  v51 = 0;
  v8 = a4;
  hMem = 0;
  v54 = 0;
  v57 = 0;
  v46 = 0;
  BufferLength = 0;
  memset(SecurityDescriptor, 0, sizeof(SecurityDescriptor));
  if ( !a4 || !a5 )
    return 87;
  if ( a6 )
    *a6 = 0;
  if ( a1 )
  {
    EnterCriticalSection(&SddlSidLookupCritical);
    gbLookupTableInitialized = 0;
  }
  InitializeSidLookupTable(1u);
  if ( a2 )
  {
    v41 = LocalAlloc(0x40u, 0x618u);
    v50 = v41;
    if ( !v41 )
    {
      LastError = 8;
      LocalFree(hMem);
      v42 = v54;
LABEL_137:
      LocalFree(v42);
      goto LABEL_35;
    }
    LastError = 0;
    memcpy_0(v41, SidLookupDomOrRootDomRelative, 0x618u);
    v12 = v50;
  }
  else
  {
    LastError = 0;
    v12 = 0;
    v50 = 0;
  }
  v13 = 0;
  v59 = 0;
  v43 = 0;
  v44 = 0;
  v45 = 0;
  v48 = 0;
  while ( v8 )
  {
    v14 = *v8;
    if ( *v8 == 68 )
    {
      if ( v8[1] != 58 || hMem )
      {
LABEL_26:
        LastError = 87;
        goto LABEL_30;
      }
      v16 = v8 + 2;
      if ( v8[2] != 40 )
      {
        v48 = 0;
        do
        {
          if ( *v16 != 32 )
            break;
          ++v16;
        }
        while ( v16 );
LABEL_59:
        for ( i = 0; (unsigned int)i < 6; i = (unsigned int)(i + 1) )
        {
          v26 = 3 * i;
          if ( ((__int64)(&ControlLookup)[3 * i + 1] & 1) != 0
            && !_wcsnicmp(v16, (&ControlLookup)[v26], *((unsigned int *)&ControlLookup + 2 * v26 + 2)) )
          {
            HIWORD(v35) = HIWORD(v48);
            LOWORD(v35) = *((_WORD *)&ControlLookup + 4 * v26 + 6) | v48;
            v36 = *((unsigned int *)&ControlLookup + 2 * v26 + 2);
            v48 = v35;
            for ( v16 += v36; v16; ++v16 )
            {
              if ( *v16 != 32 )
                break;
            }
            goto LABEL_59;
          }
        }
        v12 = v50;
        v46 = v16;
      }
      AclForString = LocalGetAclForString(v16, 1, (PACL *)&hMem, &v46, (__int64)a1, (__int64)a2, (__int64)v12, a3);
      v7 = v47;
      LastError = AclForString;
      if ( AclForString )
        goto LABEL_30;
      v8 = v46;
      v12 = v50;
      v44 = 1;
    }
    else if ( v14 )
    {
      switch ( v14 )
      {
        case 'G':
          LastError = 87;
          if ( v8[1] != 58 )
            goto LABEL_30;
          if ( v6 )
            goto LABEL_30;
          v55 = 0;
          v19 = v8 + 2;
          if ( !v19 )
            goto LABEL_30;
          v43 = 0;
          if ( !*v19 || !v19[1] )
          {
            LastError = 1332;
            goto LABEL_30;
          }
          v46 = v19 + 2;
          LastError = 0;
          v20 = LookupSidInTable(v19, 0, a1, a2, (__int64)v12, a3, (PSID *)&v55);
          if ( v20 )
          {
            v6 = (void *)v20[2];
            v21 = 0;
            v52 = (__int64)v6;
            goto LABEL_45;
          }
          v6 = (void *)v55;
          if ( v55 )
          {
            v52 = v55;
            v21 = 1;
            goto LABEL_45;
          }
          v46 -= 2;
          if ( (unsigned int)LocalConvertStringSidToSid(v19, &v52, &v46) || (LastError = GetLastError()) == 0 )
          {
            v6 = (void *)v52;
            if ( v52 )
            {
              v21 = 1;
              goto LABEL_45;
            }
          }
          else
          {
            v6 = (void *)v52;
          }
          v21 = 0;
LABEL_45:
          v43 = v21;
          if ( LastError )
            goto LABEL_30;
          v8 = v46;
          v12 = v50;
          v43 = v21;
          break;
        case 'O':
          LastError = 87;
          if ( v8[1] != 58 )
            goto LABEL_30;
          if ( v7 )
            goto LABEL_30;
          v55 = 0;
          v22 = v8 + 2;
          if ( !v22 )
            goto LABEL_30;
          if ( !*v22 || !v22[1] )
          {
            LastError = 1332;
            goto LABEL_32;
          }
          v59 = 0;
          v46 = v22 + 2;
          LastError = 0;
          v23 = LookupSidInTable(v22, 0, a1, a2, (__int64)v12, a3, (PSID *)&v55);
          if ( v23 )
          {
            v7 = (void *)v23[2];
            v24 = 0;
            v47 = v7;
            v51 = v7;
            goto LABEL_54;
          }
          v7 = (void *)v55;
          v47 = (HLOCAL)v55;
          if ( v55 )
          {
            v24 = 1;
            v51 = (void *)v55;
            v59 = 1;
            goto LABEL_54;
          }
          v46 -= 2;
          v30 = LocalpConvertStringSidToSid(v22, &v51, &v46);
          if ( v30 < 0 )
          {
            v31 = RtlNtStatusToDosError(v30);
            SetLastError(v31);
            LastError = GetLastError();
            if ( LastError )
            {
              v7 = v51;
              v47 = v51;
              goto LABEL_83;
            }
          }
          else
          {
            SetLastError(0);
          }
          v7 = v51;
          v47 = v51;
          if ( v51 )
          {
            v24 = 1;
            v59 = 1;
            goto LABEL_54;
          }
LABEL_83:
          v24 = 0;
LABEL_54:
          if ( LastError )
            goto LABEL_30;
          v8 = v46;
          v12 = v50;
          v59 = v24;
          break;
        case ' ':
          ++v8;
          break;
        default:
          if ( v54 || v14 != 83 || v8[1] != 58 )
            goto LABEL_26;
          v15 = v8 + 2;
          if ( v8[2] != 40 )
          {
            v13 = 0;
            do
            {
              if ( *v15 != 32 )
                break;
              ++v15;
            }
            while ( v15 );
LABEL_69:
            for ( j = 0; (unsigned int)j < 6; j = (unsigned int)(j + 1) )
            {
              v29 = 3 * j;
              if ( ((__int64)(&ControlLookup)[3 * j + 1] & 2) != 0
                && !_wcsnicmp(v15, (&ControlLookup)[v29], *((unsigned int *)&ControlLookup + 2 * v29 + 2)) )
              {
                v13 |= *((_WORD *)&ControlLookup + 4 * v29 + 6);
                for ( v15 += *((unsigned int *)&ControlLookup + 2 * v29 + 2); v15; ++v15 )
                {
                  if ( *v15 != 32 )
                    break;
                }
                goto LABEL_69;
              }
            }
            v12 = v50;
            v46 = v15;
          }
          v37 = LocalGetAclForString(v15, 0, (PACL *)&v54, &v46, (__int64)a1, (__int64)a2, (__int64)v12, a3);
          v7 = v47;
          LastError = v37;
          if ( v37 )
            goto LABEL_30;
          v8 = v46;
          v12 = v50;
          v45 = 1;
          break;
      }
    }
    else
    {
      v8 = 0;
    }
  }
  v17 = RtlCreateSecurityDescriptor(SecurityDescriptor, 1u);
  if ( v17 < 0 )
    LastError = RtlNtStatusToDosError(v17);
  WORD1(SecurityDescriptor[0]) |= (unsigned __int16)v48 | v13;
  if ( !LastError )
  {
    if ( !v7
      || (v38 = RtlSetOwnerSecurityDescriptor(SecurityDescriptor, v7, 0), v38 >= 0)
      || (LastError = RtlNtStatusToDosError(v38)) == 0 )
    {
      if ( !v6
        || (v40 = RtlSetGroupSecurityDescriptor(SecurityDescriptor, v6, 0), v40 >= 0)
        || (LastError = RtlNtStatusToDosError(v40)) == 0 )
      {
        if ( !v44
          || (v34 = RtlSetDaclSecurityDescriptor(SecurityDescriptor, v44, (PACL)hMem, 0), v34 >= 0)
          || (LastError = RtlNtStatusToDosError(v34)) == 0 )
        {
          if ( !v45
            || (v39 = RtlSetSaclSecurityDescriptor(SecurityDescriptor, v45, (PACL)v54, 0), v39 >= 0)
            || (LastError = RtlNtStatusToDosError(v39)) == 0 )
          {
            if ( RtlAbsoluteToSelfRelativeSD(SecurityDescriptor, *a5, &BufferLength) == -1073741789 )
            {
              v32 = LocalAlloc(0x40u, BufferLength);
              *a5 = v32;
              if ( v32 )
              {
                LastError = 0;
                v33 = RtlAbsoluteToSelfRelativeSD(SecurityDescriptor, v32, &BufferLength);
                if ( v33 >= 0 || (LastError = RtlNtStatusToDosError(v33), LocalFree(*a5), *a5 = 0, !LastError) )
                {
                  if ( a6 )
                    *a6 = BufferLength;
                }
              }
              else
              {
                LastError = 8;
              }
            }
            else
            {
              LastError = 122;
            }
          }
        }
      }
    }
  }
LABEL_30:
  if ( v59 == 1 )
    LocalFree(v7);
LABEL_32:
  if ( v43 == 1 )
    LocalFree(v6);
  LocalFree(hMem);
  LocalFree(v54);
  if ( v50 )
  {
    v42 = v50;
    goto LABEL_137;
  }
LABEL_35:
  InitializeSidLookupTable(2u);
  if ( a1 )
  {
    gbLookupTableInitialized = 0;
    LeaveCriticalSection(&SddlSidLookupCritical);
  }
  return LastError;
}

```

## disassembly

```asm
0x180005d00  mov     [rsp-8+arg_10], r8b
0x180005d05  push    rbp
0x180005d06  push    rbx
0x180005d07  push    rsi
0x180005d08  push    r12
0x180005d0a  push    r13
0x180005d0c  push    r14
0x180005d0e  lea     rbp, [rsp-1Fh]
0x180005d13  sub     rsp, 0C8h
0x180005d1a  xor     esi, esi
0x180005d1c  xor     eax, eax
0x180005d1e  xor     r14d, r14d
0x180005d21  mov     [rbp+47h+var_80], rsi
0x180005d25  mov     [rbp+47h+var_A0], r14
0x180005d29  xorps   xmm0, xmm0
0x180005d2c  mov     [rbp+47h+var_88], r14
0x180005d30  mov     rbx, r9
0x180005d33  mov     [rbp+47h+hMem], rsi
0x180005d37  mov     r13, rdx
0x180005d3a  mov     [rbp+47h+var_70], rsi
0x180005d3e  mov     r12, rcx
0x180005d41  mov     [rbp+47h+var_40], rax
0x180005d45  mov     [rbp+47h+var_A8], rax
0x180005d49  mov     [rbp+47h+BufferLength], eax
0x180005d4c  movups  [rbp+47h+SecurityDescriptor], xmm0
0x180005d50  movups  [rbp+47h+var_50], xmm0
0x180005d54  test    r9, r9
0x180005d57  jz      loc_180006530
0x180005d5d  cmp     [rbp+47h+arg_20], rax
0x180005d61  jz      loc_180006530
0x180005d67  mov     rax, [rbp+47h+arg_28]
0x180005d6b  mov     [rsp+0F0h+arg_0], rdi
0x180005d73  test    rax, rax
0x180005d76  jnz     loc_180006447
0x180005d7c  test    r12, r12
0x180005d7f  jnz     loc_18000644E
0x180005d85  mov     cl, 1
0x180005d87  call    InitializeSidLookupTable
0x180005d8c  test    r13, r13
0x180005d8f  jnz     loc_180006466
0x180005d95  xor     edi, edi
0x180005d97  xor     ecx, ecx
0x180005d99  mov     [rbp+47h+var_90], rcx
0x180005d9d  mov     [rsp+0F0h+var_30], r15
0x180005da5  xor     r15d, r15d
0x180005da8  mov     [rbp+47h+arg_18], sil
0x180005dac  mov     [rbp+47h+var_B0], sil
0x180005db0  mov     [rbp+47h+var_AF], sil
0x180005db4  mov     [rbp+47h+var_AE], sil
0x180005db8  mov     [rbp+47h+var_98], esi
0x180005dbb  lea     rdx, ControlLookup
0x180005dc2  test    rbx, rbx
0x180005dc5  jz      loc_180005E61
0x180005dcb  movzx   eax, word ptr [rbx]
0x180005dce  cmp     ax, 44h ; 'D'
0x180005dd2  jz      short loc_180005E23
0x180005dd4  test    ax, ax
0x180005dd7  jz      short loc_180005E4E
0x180005dd9  cmp     ax, 47h ; 'G'
0x180005ddd  jz      loc_180005EF8
0x180005de3  cmp     ax, 4Fh ; 'O'
0x180005de7  jz      loc_180005F8E
0x180005ded  cmp     ax, 20h ; ' '
0x180005df1  jz      loc_1800064B4
0x180005df7  cmp     [rbp+47h+var_70], 0
0x180005dfc  jnz     short loc_180005E5A
0x180005dfe  cmp     ax, 53h ; 'S'
0x180005e02  jnz     short loc_180005E5A
0x180005e04  cmp     word ptr [rbx+2], 3Ah ; ':'
0x180005e09  jnz     short loc_180005E5A
0x180005e0b  cmp     word ptr [rbx+4], 28h ; '('
0x180005e10  lea     r14, [rbx+4]
0x180005e14  jnz     loc_1800060B4
0x180005e1a  test    edi, edi
0x180005e1c  jnz     short loc_180005E48
0x180005e1e  jmp     loc_180006360
0x180005e23  cmp     word ptr [rbx+2], 3Ah ; ':'
0x180005e28  jnz     short loc_180005E5A
0x180005e2a  cmp     [rbp+47h+hMem], 0
0x180005e2f  jnz     short loc_180005E5A
0x180005e31  cmp     word ptr [rbx+4], 28h ; '('
0x180005e36  lea     r14, [rbx+4]
0x180005e3a  jnz     loc_180006030
0x180005e40  test    edi, edi
0x180005e42  jz      loc_18000606C
0x180005e48  mov     r14, [rbp+47h+var_A0]
0x180005e4c  jmp     short loc_180005E90
0x180005e4e  xor     ebx, ebx
0x180005e50  test    edi, edi
0x180005e52  jz      loc_180005DC2
0x180005e58  jmp     short loc_180005E90
0x180005e5a  mov     edi, 57h ; 'W'
0x180005e5f  jmp     short loc_180005E90
0x180005e61  test    edi, edi
0x180005e63  jnz     short loc_180005E90
0x180005e65  mov     edx, 1; Revision
0x180005e6a  lea     rcx, [rbp+47h+SecurityDescriptor]; SecurityDescriptor
0x180005e6e  call    cs:__imp_RtlCreateSecurityDescriptor
0x180005e74  test    eax, eax
0x180005e76  js      loc_1800064D1
0x180005e7c  mov     eax, [rbp+47h+var_98]
0x180005e7f  or      r15w, ax
0x180005e83  or      word ptr [rbp+47h+SecurityDescriptor+2], r15w
0x180005e88  test    edi, edi
0x180005e8a  jz      loc_1800063A8
0x180005e90  cmp     [rbp+47h+arg_18], 1
0x180005e94  jz      loc_1800064EA
0x180005e9a  cmp     [rbp+47h+var_B0], 1
0x180005e9e  mov     r15, [rsp+0F0h+var_30]
0x180005ea6  jz      loc_1800064F8
0x180005eac  mov     rcx, [rbp+47h+hMem]; hMem
0x180005eb0  call    cs:__imp_LocalFree
0x180005eb6  mov     rcx, [rbp+47h+var_70]; hMem
0x180005eba  call    cs:__imp_LocalFree
0x180005ec0  mov     rax, [rbp+47h+var_90]
0x180005ec4  test    rax, rax
0x180005ec7  jnz     loc_180006506
0x180005ecd  mov     cl, 2
0x180005ecf  call    InitializeSidLookupTable
0x180005ed4  test    r12, r12
0x180005ed7  jnz     loc_180006514
0x180005edd  mov     eax, edi
0x180005edf  mov     rdi, [rsp+0F0h+arg_0]
0x180005ee7  add     rsp, 0C8h
0x180005eee  pop     r14
0x180005ef0  pop     r13
0x180005ef2  pop     r12
0x180005ef4  pop     rsi
0x180005ef5  pop     rbx
0x180005ef6  pop     rbp
0x180005ef7  retn
0x180005ef8  cmp     word ptr [rbx+2], 3Ah ; ':'
0x180005efd  mov     edi, 57h ; 'W'
0x180005f02  jnz     short loc_180005E90
0x180005f04  test    rsi, rsi
0x180005f07  jnz     short loc_180005E90
0x180005f09  mov     [rbp+47h+var_68], rsi
0x180005f0d  add     rbx, 4
0x180005f11  jz      loc_180005E90
0x180005f17  mov     [rbp+47h+var_B0], sil
0x180005f1b  cmp     [rbx], si
0x180005f1e  jz      loc_1800064C7
0x180005f24  cmp     [rbx+2], si
0x180005f28  jz      loc_1800064C7
0x180005f2e  lea     rax, [rbx+4]
0x180005f32  mov     r9, r13
0x180005f35  mov     [rbp+47h+var_A8], rax
0x180005f39  mov     r8, r12
0x180005f3c  lea     rax, [rbp+47h+var_68]
0x180005f40  xor     edx, edx; Sid
0x180005f42  mov     [rsp+0F0h+var_C0], rax; __int64
0x180005f47  xor     edi, edi
0x180005f49  movzx   eax, [rbp+47h+arg_10]
0x180005f4d  mov     [rsp+0F0h+var_C8], al; char
0x180005f51  mov     [rsp+0F0h+var_D0], rcx; __int64
0x180005f56  mov     rcx, rbx; String1
0x180005f59  call    LookupSidInTable
0x180005f5e  test    rax, rax
0x180005f61  jz      loc_180006149
0x180005f67  mov     rsi, [rax+10h]
0x180005f6b  movzx   eax, dil
0x180005f6f  mov     [rbp+47h+var_80], rsi
0x180005f73  mov     [rbp+47h+var_B0], al
0x180005f76  test    edi, edi
0x180005f78  jnz     loc_180005E90
0x180005f7e  mov     rbx, [rbp+47h+var_A8]
0x180005f82  mov     rcx, [rbp+47h+var_90]
0x180005f86  mov     [rbp+47h+var_B0], al
0x180005f89  jmp     loc_180005DBB
0x180005f8e  cmp     word ptr [rbx+2], 3Ah ; ':'
0x180005f93  mov     edi, 57h ; 'W'
0x180005f98  jnz     loc_180005E90
0x180005f9e  test    r14, r14
0x180005fa1  jnz     loc_180005E90
0x180005fa7  mov     [rbp+47h+var_68], r14
0x180005fab  add     rbx, 4
0x180005faf  jz      loc_180005E90
0x180005fb5  cmp     [rbx], r14w
0x180005fb9  jz      loc_1800064BD
0x180005fbf  cmp     [rbx+2], r14w
0x180005fc4  jz      loc_1800064BD
0x180005fca  xor     al, al
0x180005fcc  mov     r9, r13
0x180005fcf  mov     [rbp+47h+arg_18], al
0x180005fd2  mov     r8, r12
0x180005fd5  lea     rax, [rbx+4]
0x180005fd9  xor     edx, edx; Sid
0x180005fdb  mov     [rbp+47h+var_A8], rax
0x180005fdf  xor     edi, edi
0x180005fe1  lea     rax, [rbp+47h+var_68]
0x180005fe5  mov     [rsp+0F0h+var_C0], rax; __int64
0x180005fea  movzx   eax, [rbp+47h+arg_10]
0x180005fee  mov     [rsp+0F0h+var_C8], al; char
0x180005ff2  mov     [rsp+0F0h+var_D0], rcx; __int64
0x180005ff7  mov     rcx, rbx; String1
0x180005ffa  call    LookupSidInTable
0x180005fff  test    rax, rax
0x180006002  jz      loc_1800060F6
0x180006008  mov     r14, [rax+10h]
0x18000600c  movzx   eax, dil
0x180006010  mov     [rbp+47h+var_A0], r14
0x180006014  mov     [rbp+47h+var_88], r14
0x180006018  test    edi, edi
0x18000601a  jnz     loc_180005E90
0x180006020  mov     rbx, [rbp+47h+var_A8]
0x180006024  mov     rcx, [rbp+47h+var_90]
0x180006028  mov     [rbp+47h+arg_18], al
0x18000602b  jmp     loc_180005DBB
0x180006030  xor     eax, eax
0x180006032  mov     [rbp+47h+var_98], eax
0x180006035  cmp     word ptr [r14], 20h ; ' '
0x18000603a  jnz     short loc_180006042
0x18000603c  add     r14, 2
0x180006040  jnz     short loc_180006035
0x180006042  xor     ebx, ebx
0x180006044  cmp     ebx, 6
0x180006047  jnb     short loc_180006064
0x180006049  lea     rcx, [rbx+rbx*2]
0x18000604d  lea     rdi, ds:0[rcx*8]
0x180006055  test    byte ptr [rdi+rdx+10h], 1
0x18000605a  jnz     loc_1800062A0
0x180006060  inc     ebx
0x180006062  jmp     short loc_180006044
0x180006064  mov     rcx, [rbp+47h+var_90]
0x180006068  mov     [rbp+47h+var_A8], r14
0x18000606c  movzx   eax, [rbp+47h+arg_10]
0x180006070  lea     r9, [rbp+47h+var_A8]
0x180006074  mov     [rsp+0F0h+var_B8], al; char
0x180006078  lea     r8, [rbp+47h+hMem]
0x18000607c  mov     [rsp+0F0h+var_C0], rcx; __int64
0x180006081  mov     dl, 1
0x180006083  mov     qword ptr [rsp+0F0h+var_C8], r13; __int64
0x180006088  mov     rcx, r14; String1
0x18000608b  mov     [rsp+0F0h+var_D0], r12; __int64
0x180006090  call    LocalGetAclForString
0x180006095  mov     r14, [rbp+47h+var_A0]
0x180006099  mov     edi, eax
0x18000609b  test    eax, eax
0x18000609d  jnz     loc_180005E90
0x1800060a3  mov     rbx, [rbp+47h+var_A8]
0x1800060a7  mov     rcx, [rbp+47h+var_90]
0x1800060ab  mov     [rbp+47h+var_AF], 1
0x1800060af  jmp     loc_180005DBB
0x1800060b4  xor     eax, eax
0x1800060b6  movzx   r15d, ax
0x1800060ba  cmp     word ptr [r14], 20h ; ' '
0x1800060bf  jnz     short loc_1800060D0
0x1800060c1  add     r14, 2
0x1800060c5  jnz     short loc_1800060BA
0x1800060c7  nop     word ptr [rax+rax+00000000h]
0x1800060d0  xor     ebx, ebx
0x1800060d2  cmp     ebx, 6
0x1800060d5  jnb     loc_180006358
0x1800060db  lea     rcx, [rbx+rbx*2]
0x1800060df  lea     rdi, ds:0[rcx*8]
0x1800060e7  test    byte ptr [rdi+rdx+10h], 2
0x1800060ec  jnz     loc_18000630A
0x1800060f2  inc     ebx
0x1800060f4  jmp     short loc_1800060D2
0x1800060f6  mov     r14, [rbp+47h+var_68]
0x1800060fa  mov     [rbp+47h+var_A0], r14
0x1800060fe  test    r14, r14
0x180006101  jz      short loc_180006111
0x180006103  mov     al, 1
0x180006105  mov     [rbp+47h+var_88], r14
0x180006109  mov     [rbp+47h+arg_18], al
0x18000610c  jmp     loc_180006018
0x180006111  sub     [rbp+47h+var_A8], 4
0x180006116  lea     r8, [rbp+47h+var_A8]
0x18000611a  lea     rdx, [rbp+47h+var_88]
0x18000611e  mov     rcx, rbx
0x180006121  call    LocalpConvertStringSidToSid
0x180006126  test    eax, eax
0x180006128  js      short loc_18000615D
0x18000612a  xor     ecx, ecx; dwErrCode
0x18000612c  call    cs:__imp_SetLastError
0x180006132  mov     r14, [rbp+47h+var_88]
0x180006136  mov     [rbp+47h+var_A0], r14
0x18000613a  test    r14, r14
0x18000613d  jz      short loc_180006181
0x18000613f  mov     al, 1
0x180006141  mov     [rbp+47h+arg_18], al
0x180006144  jmp     loc_180006018
0x180006149  mov     rsi, [rbp+47h+var_68]
0x18000614d  test    rsi, rsi
0x180006150  jz      short loc_18000618A
0x180006152  mov     [rbp+47h+var_80], rsi
0x180006156  mov     al, 1
0x180006158  jmp     loc_180005F73
0x18000615d  mov     ecx, eax; Status
0x18000615f  call    cs:__imp_RtlNtStatusToDosError
0x180006165  mov     ecx, eax; dwErrCode
0x180006167  call    cs:__imp_SetLastError
0x18000616d  call    cs:__imp_GetLastError
0x180006173  mov     edi, eax
0x180006175  test    eax, eax
0x180006177  jz      short loc_180006132
0x180006179  mov     r14, [rbp+47h+var_88]
0x18000617d  mov     [rbp+47h+var_A0], r14
0x180006181  movzx   eax, [rbp+47h+arg_18]
  ... truncated ...
```
