# EventWriteHelper

- ea: `0x18000a850`
- end: `0x18000b1f9`
- name: `EventWriteHelper`
- size: `2473`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000a7e0`
- `0x18000a818`

## callees

- `0x180003ac0`
- `0x18000a850`
- `0x18000b660`
- `0x180018138`
- `0x180018dfc`
- `0x18001d9a0`
- `0x18003d270`
- `0x18003dd2c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000a97d`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000a9ae`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000a97d`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000a9ae`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000a9e1`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000aa1f`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000ab57`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000abc6`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000ad1c`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000adac`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000aeec`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000afbc`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000b05e`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000a9e1`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000aa1f`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000ab57`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000abc6`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000ad1c`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000adac`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000aeec`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000afbc`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000b05e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b181`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b181`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000af93`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000af93`
- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x18000a938`
- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x18000a938`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18000abf8`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18000abf8`
- `ntdll!RtlReleaseResource` at `0x18000aeb4`
- `ntdll!RtlReleaseResource` at `0x18000af45`
- `ntdll!RtlReleaseResource` at `0x18000b15e`
- `ntdll!RtlReleaseResource` at `0x18000aeb4`
- `ntdll!RtlReleaseResource` at `0x18000af45`
- `ntdll!RtlReleaseResource` at `0x18000b15e`
- `ntdll!RtlAcquireResourceShared` at `0x18000ab03`
- `ntdll!RtlAcquireResourceShared` at `0x18000ae6b`
- `ntdll!RtlAcquireResourceShared` at `0x18000b117`
- `ntdll!RtlAcquireResourceShared` at `0x18000ab03`
- `ntdll!RtlAcquireResourceShared` at `0x18000ae6b`
- `ntdll!RtlAcquireResourceShared` at `0x18000b117`
- `ntdll!RtlInitUnicodeString` at `0x18000aaa5`
- `ntdll!RtlInitUnicodeString` at `0x18000ac67`
- `ntdll!RtlInitUnicodeString` at `0x18000adf6`
- `ntdll!RtlInitUnicodeString` at `0x18000b007`
- `ntdll!RtlInitUnicodeString` at `0x18000b0a2`
- `ntdll!RtlInitUnicodeString` at `0x18000aaa5`
- `ntdll!RtlInitUnicodeString` at `0x18000ac67`
- `ntdll!RtlInitUnicodeString` at `0x18000adf6`
- `ntdll!RtlInitUnicodeString` at `0x18000b007`
- `ntdll!RtlInitUnicodeString` at `0x18000b0a2`

## pseudocode

```c
__int64 __fastcall EventWriteHelper(REGHANDLE *a1, const EVENT_DESCRIPTOR *a2, _WORD *a3, int a4, FILETIME *a5)
{
  const EVENT_DESCRIPTOR *v5; // rbx
  REGHANDLE *v6; // rdi
  struct _EVENT_DATA_DESCRIPTOR *v8; // r13
  int v10; // r15d
  unsigned __int64 v11; // rsi
  _WORD *v12; // rax
  __int64 v13; // rcx
  unsigned int m; // ebx
  void *v15; // rcx
  __int64 j; // rdi
  _QWORD *v18; // rax
  FILETIME v19; // r15
  __int64 v20; // rbx
  const WCHAR *v21; // rdx
  __int64 v22; // rbx
  int v23; // eax
  char v24; // bl
  __int64 v25; // r8
  _DWORD *v26; // rax
  DWORD v27; // r15d
  __int64 v28; // rbx
  const WCHAR *v29; // rax
  __int64 v30; // rbx
  PWSTR v31; // rax
  PWSTR v32; // rdx
  const wchar_t *v33; // rcx
  unsigned __int16 *v34; // r15
  __int64 v35; // rbx
  ULONGLONG v36; // rax
  _DWORD *v37; // rax
  DWORD dwLowDateTime; // r15d
  __int64 v39; // rbx
  DWORD v40; // eax
  const unsigned __int16 *v41; // r15
  __int64 v42; // rax
  WCHAR *v43; // rax
  __int64 v44; // rbx
  PWSTR v45; // rax
  char v46; // di
  __int64 i; // rdx
  _QWORD *v48; // rax
  __int64 v49; // rbx
  WCHAR *v50; // rax
  FILETIME v51; // r9
  __int64 v52; // rbx
  PWSTR v53; // rax
  WCHAR *v54; // rax
  FILETIME v55; // r9
  __int64 v56; // rbx
  PWSTR v57; // rax
  char v58; // bl
  __int64 k; // rdx
  LPWSTR lpBuffer; // [rsp+28h] [rbp-E0h]
  DWORD nSize[2]; // [rsp+30h] [rbp-D8h]
  va_list *Arguments; // [rsp+38h] [rbp-D0h]
  __int64 v63; // [rsp+40h] [rbp-C8h]
  __int64 v64; // [rsp+48h] [rbp-C0h]
  __int64 v65; // [rsp+50h] [rbp-B8h]
  struct _UNICODE_STRING v66; // [rsp+58h] [rbp-B0h] BYREF
  PCWSTR v67; // [rsp+68h] [rbp-A0h]
  WCHAR Buffer[4]; // [rsp+70h] [rbp-98h] BYREF
  PCWSTR SourceString; // [rsp+78h] [rbp-90h]
  int v70; // [rsp+80h] [rbp-88h]
  REGHANDLE *v71; // [rsp+88h] [rbp-80h]
  FILETIME FileTime; // [rsp+90h] [rbp-78h] BYREF
  unsigned __int64 v73; // [rsp+98h] [rbp-70h]
  const EVENT_DESCRIPTOR *v74; // [rsp+A0h] [rbp-68h]
  struct _UNICODE_STRING DestinationString; // [rsp+A8h] [rbp-60h] BYREF
  _SYSTEMTIME SystemTime; // [rsp+B8h] [rbp-50h] BYREF
  void *Block[128]; // [rsp+C8h] [rbp-40h] BYREF

  v5 = a2;
  v6 = a1;
  v8 = 0;
  v74 = a2;
  v71 = a1;
  v10 = a4;
  v70 = a4;
  v66 = 0;
  memset_0(Block, 0, 0x3F8u);
  *(_QWORD *)Buffer = 0;
  if ( v5 )
  {
    LODWORD(v11) = 0;
    if ( _InterlockedCompareExchange(&_lLoggingEnabled, 0, 0)
      && _pflstate
      && *((_BYTE *)_pflstate + 315)
      && RtlAcquireResourceShared((PRTL_RESOURCE)((char *)_pflstate + 80), 1u) )
    {
      v46 = 0;
      for ( i = *((_QWORD *)_pflstate + 3); i && *(_DWORD *)i <= 0x12Eu; i = *(_QWORD *)(i + 8) )
      {
        if ( (unsigned int)(*(_DWORD *)(i + 4) + *(_DWORD *)i) > 0x12E )
        {
          v46 = 1;
          break;
        }
      }
      RtlReleaseResource((PRTL_RESOURCE)((char *)_pflstate + 80));
      if ( v46 )
        FileLogAdd(L"W32timeEvent Id:%d Channel:%d Level:%d\n", v5->Id, v5->Channel, v5->Level);
      v6 = v71;
    }
    if ( a3 )
    {
      v12 = a3;
      v13 = 128;
      while ( *v12 )
      {
        ++v12;
        if ( !--v13 )
          goto LABEL_11;
      }
      v11 = 128 - v13;
      v8 = (struct _EVENT_DATA_DESCRIPTOR *)malloc(16 * (128 - v13));
      if ( v8 )
      {
        for ( j = 0; ; j = (unsigned int)(j + 1) )
        {
          if ( (unsigned int)j >= v11 )
          {
            v5 = v74;
            v10 = v70;
            v6 = v71;
            goto LABEL_9;
          }
          if ( a3[j] == 105 )
          {
            v18 = malloc(8u);
            Block[j] = v18;
            if ( !v18 )
              break;
            v19 = *a5;
            v20 = (unsigned int)j;
            *v18 = *a5++;
            v8[v20].Ptr = (ULONGLONG)v18;
            *(_QWORD *)&v8[v20].Size = 8;
            if ( _InterlockedCompareExchange(&_lLoggingEnabled, 0, 0)
              && _pflstate
              && *((_BYTE *)_pflstate + 315)
              && RtlAcquireResourceShared((PRTL_RESOURCE)((char *)_pflstate + 80), 1u) )
            {
              v58 = 0;
              for ( k = *((_QWORD *)_pflstate + 3); k && *(_DWORD *)k <= 0x12Eu; k = *(_QWORD *)(k + 8) )
              {
                if ( (unsigned int)(*(_DWORD *)(k + 4) + *(_DWORD *)k) > 0x12E )
                {
                  v58 = 1;
                  break;
                }
              }
              RtlReleaseResource((PRTL_RESOURCE)((char *)_pflstate + 80));
              if ( v58 )
              {
                v33 = L"UINT64 param: %I64u\n";
LABEL_97:
                v32 = (PWSTR)v19;
LABEL_45:
                FileLogAppend(v33, v32);
                continue;
              }
            }
          }
          else
          {
            switch ( a3[j] )
            {
              case 'D':
                v37 = malloc(4u);
                Block[j] = v37;
                if ( !v37 )
                  goto LABEL_11;
                dwLowDateTime = a5->dwLowDateTime;
                v39 = (unsigned int)j;
                *v37 = a5->dwLowDateTime;
                ++a5;
                v8[v39].Ptr = (ULONGLONG)v37;
                *(_QWORD *)&v8[v39].Size = 4;
                if ( (unsigned __int8)FileLogAllowEntry(302) )
                  FileLogAppend(L"INT32 param: %d\n", dwLowDateTime);
                continue;
              case 'I':
                v48 = malloc(8u);
                Block[j] = v48;
                if ( !v48 )
                  goto LABEL_11;
                v19 = *a5;
                v49 = (unsigned int)j;
                *v48 = *a5++;
                v8[v49].Ptr = (ULONGLONG)v48;
                *(_QWORD *)&v8[v49].Size = 8;
                if ( !(unsigned __int8)FileLogAllowEntry(302) )
                  continue;
                v33 = L"INT64 param: %I64d\n";
                goto LABEL_97;
              case 'S':
                v19 = *a5;
                v21 = (const WCHAR *)*a5;
                DestinationString = 0;
                ++a5;
                RtlInitUnicodeString(&DestinationString, v21);
                v22 = (unsigned int)j;
                v8[v22].Ptr = (ULONGLONG)DestinationString.Buffer;
                v23 = DestinationString.Length + 2;
                v8[v22].Reserved = 0;
                v8[v22].Size = v23;
                if ( !_InterlockedCompareExchange(&_lLoggingEnabled, 0, 0)
                  || !_pflstate
                  || !*((_BYTE *)_pflstate + 315)
                  || !RtlAcquireResourceShared((PRTL_RESOURCE)((char *)_pflstate + 80), 1u) )
                {
                  continue;
                }
                v24 = 0;
                v25 = *((_QWORD *)_pflstate + 3);
                break;
              case 'T':
                FileTime = 0;
                SystemTime = 0;
                v29 = (const WCHAR *)malloc(0xC8u);
                SourceString = v29;
                Block[j] = (void *)v29;
                if ( !v29 )
                  goto LABEL_11;
                FileTime = *a5++;
                if ( !FileTimeToSystemTime(&FileTime, &SystemTime) )
                  SystemTime = 0;
                LODWORD(v65) = SystemTime.wMilliseconds;
                LODWORD(v64) = SystemTime.wSecond;
                LODWORD(v63) = SystemTime.wMinute;
                LODWORD(Arguments) = SystemTime.wHour;
                nSize[0] = SystemTime.wDay;
                LODWORD(lpBuffer) = SystemTime.wMonth;
                StringCchPrintfW(
                  (unsigned __int16 *)SourceString,
                  0x64u,
                  L"%04u-%02u-%02uT%02u:%02u:%02u.%uZ",
                  SystemTime.wYear,
                  lpBuffer,
                  *(_QWORD *)nSize,
                  Arguments,
                  v63,
                  v64,
                  v65);
                RtlInitUnicodeString(&v66, SourceString);
                v30 = (unsigned int)j;
                v31 = v66.Buffer;
                v8[v30].Size = v66.Length + 2;
                v8[v30].Ptr = (ULONGLONG)v31;
                v8[v30].Reserved = 0;
                if ( !(unsigned __int8)FileLogAllowEntry(302) )
                  continue;
                v32 = v66.Buffer;
                v33 = L"SYSTEMTIME param: %s\n";
                goto LABEL_45;
              case 'd':
                v26 = malloc(4u);
                Block[j] = v26;
                if ( !v26 )
                  goto LABEL_11;
                v27 = a5->dwLowDateTime;
                v28 = (unsigned int)j;
                *v26 = a5->dwLowDateTime;
                ++a5;
                v8[v28].Ptr = (ULONGLONG)v26;
                *(_QWORD *)&v8[v28].Size = 4;
                if ( (unsigned __int8)FileLogAllowEntry(302) )
                  FileLogAppend(L"UINT32 param: %u\n", v27);
                continue;
              case 'e':
                v40 = a5->dwLowDateTime;
                LODWORD(SourceString) = v40;
                if ( v40 )
                {
                  FormatMessageW(0x1300u, 0, v40, 0, Buffer, 0, 0);
                  v41 = &qword_180071478;
                  if ( *(_QWORD *)Buffer )
                    v41 = *(const unsigned __int16 **)Buffer;
                }
                else
                {
                  v41 = (const unsigned __int16 *)g_pwszSuccessMsg;
                }
                v42 = -1;
                do
                  ++v42;
                while ( v41[v42] );
                v73 = v42 + 20;
                v43 = (WCHAR *)malloc(2 * (v42 + 20));
                v67 = v43;
                Block[j] = v43;
                if ( !v43 )
                  goto LABEL_11;
                ++a5;
                StringCchPrintfW(v43, v73, L"0x%08X: %ls.", (unsigned int)SourceString, v41);
                RtlInitUnicodeString(&v66, v67);
                v44 = (unsigned int)j;
                v45 = v66.Buffer;
                v8[v44].Size = v66.Length + 2;
                v8[v44].Ptr = (ULONGLONG)v45;
                v8[v44].Reserved = 0;
                if ( (unsigned __int8)FileLogAllowEntry(302) )
                  FileLogAppend(L"Error param: %s\n", v66.Buffer);
                continue;
              case 'f':
                v50 = (WCHAR *)malloc(0xC8u);
                v67 = v50;
                Block[j] = v50;
                if ( !v50 )
                  goto LABEL_11;
                v51 = *a5++;
                StringCchPrintfW(v50, 0x64u, L"%0.5f", v51);
                RtlInitUnicodeString(&v66, v67);
                v52 = (unsigned int)j;
                v53 = v66.Buffer;
                v8[v52].Size = v66.Length + 2;
                v8[v52].Ptr = (ULONGLONG)v53;
                v8[v52].Reserved = 0;
                if ( (unsigned __int8)FileLogAllowEntry(302) )
                  FileLogAppend(L"Float param: %s\n", v66.Buffer);
                continue;
              case 'u':
                v34 = (unsigned __int16 *)*a5;
                v35 = (unsigned int)j;
                ++a5;
                v36 = *((_QWORD *)v34 + 1);
                v8[v35].Size = *v34 + 2;
                v8[v35].Ptr = v36;
                v8[v35].Reserved = 0;
                if ( (unsigned __int8)FileLogAllowEntry(302) )
                  FileLogAppend(L"UnicodeString param: %s\n", *((_QWORD *)v34 + 1));
                continue;
              case 'x':
                v54 = (WCHAR *)malloc(0xC8u);
                v67 = v54;
                Block[j] = v54;
                if ( !v54 )
                  goto LABEL_11;
                v55 = *a5++;
                StringCchPrintfW(v54, 0x64u, L"0x%016I64x", v55);
                RtlInitUnicodeString(&v66, v67);
                v56 = (unsigned int)j;
                v57 = v66.Buffer;
                v8[v56].Size = v66.Length + 2;
                v8[v56].Ptr = (ULONGLONG)v57;
                v8[v56].Reserved = 0;
                if ( (unsigned __int8)FileLogAllowEntry(302) )
                  FileLogAppend(L"UINT64 Hex param: %s\n", v66.Buffer);
                continue;
              default:
                goto LABEL_11;
            }
            while ( v25 && *(_DWORD *)v25 <= 0x12Eu )
            {
              if ( (unsigned int)(*(_DWORD *)(v25 + 4) + *(_DWORD *)v25) > 0x12E )
              {
                v24 = 1;
                break;
              }
              v25 = *(_QWORD *)(v25 + 8);
            }
            RtlReleaseResource((PRTL_RESOURCE)((char *)_pflstate + 80));
            if ( v24 )
            {
              v33 = L"WSTR param: %s\n";
              goto LABEL_97;
            }
          }
        }
      }
    }
    else
    {
LABEL_9:
      if ( v10 )
        CEventWrite((_DWORD)v6, (_DWORD)v5, v11, (_DWORD)v8, v10);
      else
        EventWrite(*v6, v5, v11, v8);
    }
  }
LABEL_11:
  for ( m = 0; m < 0x7F; ++m )
  {
    v15 = Block[m];
    if ( v15 )
      free(v15);
  }
  if ( *(_QWORD *)Buffer )
  {
    LocalFree(*(HLOCAL *)Buffer);
    *(_QWORD *)Buffer = 0;
  }
  if ( v8 )
    free(v8);
  return 0;
}

```

## disassembly

```asm
0x18000a850  mov     r11, rsp
0x18000a853  push    rbp
0x18000a854  push    r13
0x18000a856  lea     rbp, [r11-408h]
0x18000a85d  sub     rsp, 4F8h
0x18000a864  mov     rax, cs:__security_cookie
0x18000a86b  xor     rax, rsp
0x18000a86e  mov     [rbp+400h+var_40], rax
0x18000a875  mov     [r11+18h], rbx
0x18000a879  xorps   xmm0, xmm0
0x18000a87c  mov     [r11-20h], rdi
0x18000a880  mov     rbx, rdx
0x18000a883  mov     [r11-28h], r12
0x18000a887  mov     rdi, rcx
0x18000a88a  mov     r12, [rbp+400h+arg_20]
0x18000a891  xor     r13d, r13d
0x18000a894  mov     [r11-30h], r14
0x18000a898  mov     r14, r8
0x18000a89b  mov     [rbp+400h+var_468], rdx
0x18000a89f  mov     r8d, 3F8h; Size
0x18000a8a5  mov     [rbp+400h+var_480], rcx
0x18000a8a9  xor     edx, edx; Val
0x18000a8ab  mov     [r11-38h], r15
0x18000a8af  lea     rcx, [rbp+400h+Block]; void *
0x18000a8b3  mov     r15d, r9d
0x18000a8b6  mov     [rsp+500h+var_488], r9d
0x18000a8bb  movups  xmmword ptr [rsp+500h+var_4B8.Buffer], xmm0
0x18000a8c0  call    memset_0
0x18000a8c5  mov     qword ptr [rsp+500h+Buffer], r13
0x18000a8ca  test    rbx, rbx
0x18000a8cd  jz      short loc_18000A94C
0x18000a8cf  mov     [rsp+4F0h], rsi
0x18000a8d7  xor     ecx, ecx
0x18000a8d9  xor     esi, esi
0x18000a8db  xor     eax, eax
0x18000a8dd  lock cmpxchg cs:?_lLoggingEnabled@@3JC, ecx; long volatile _lLoggingEnabled
0x18000a8e5  jnz     loc_18000AE48
0x18000a8eb  test    r14, r14
0x18000a8ee  jz      short loc_18000A923
0x18000a8f0  mov     esi, 80h
0x18000a8f5  mov     rax, r14
0x18000a8f8  mov     ecx, esi
0x18000a8fa  nop     word ptr [rax+rax+00h]
0x18000a900  cmp     [rax], r13w
0x18000a904  jz      loc_18000A9D7
0x18000a90a  add     rax, 2
0x18000a90e  sub     rcx, 1
0x18000a912  jnz     short loc_18000A900
0x18000a914  jmp     short def_18000AA8A; jumptable 000000018000AA8A default case, cases 69-72,74-82,85-99,103-116,118,119
0x18000a916  mov     rbx, [rbp+400h+var_468]
0x18000a91a  mov     r15d, [rsp+500h+var_488]
0x18000a91f  mov     rdi, [rbp+400h+var_480]
0x18000a923  mov     r9, r13; UserData
0x18000a926  mov     r8d, esi; UserDataCount
0x18000a929  mov     rdx, rbx; EventDescriptor
0x18000a92c  test    r15d, r15d
0x18000a92f  jnz     loc_18000ACBE
0x18000a935  mov     rcx, [rdi]; RegHandle
0x18000a938  call    cs:__imp_EventWrite
0x18000a93f  nop     dword ptr [rax+rax+00h]
0x18000a944  mov     rsi, [rsp+4F0h]; jumptable 000000018000AA8A default case, cases 69-72,74-82,85-99,103-116,118,119
0x18000a94c  mov     r15, [rsp+500h+var_30]
0x18000a954  xor     ebx, ebx
0x18000a956  mov     r14, [rsp+500h+var_28]
0x18000a95e  mov     r12, [rsp+500h+var_20]
0x18000a966  mov     rdi, [rsp+500h+var_18]
0x18000a96e  xchg    ax, ax
0x18000a970  movsxd  rax, ebx
0x18000a973  mov     rcx, [rbp+rax*8+400h+Block]; Block
0x18000a978  test    rcx, rcx
0x18000a97b  jz      short loc_18000A989
0x18000a97d  call    cs:__imp_free
0x18000a984  nop     dword ptr [rax+rax+00h]
0x18000a989  inc     ebx
0x18000a98b  cmp     ebx, 7Fh
0x18000a98e  jb      short loc_18000A970
0x18000a990  mov     rcx, qword ptr [rsp+500h+Buffer]; hMem
0x18000a995  mov     rbx, [rsp+500h+arg_10]
0x18000a99d  test    rcx, rcx
0x18000a9a0  jnz     loc_18000B181
0x18000a9a6  test    r13, r13
0x18000a9a9  jz      short loc_18000A9BA
0x18000a9ab  mov     rcx, r13; Block
0x18000a9ae  call    cs:__imp_free
0x18000a9b5  nop     dword ptr [rax+rax+00h]
0x18000a9ba  xor     eax, eax
0x18000a9bc  mov     rcx, [rbp+400h+var_40]
0x18000a9c3  xor     rcx, rsp; StackCookie
0x18000a9c6  call    __security_check_cookie
0x18000a9cb  add     rsp, 4F8h
0x18000a9d2  pop     r13
0x18000a9d4  pop     rbp
0x18000a9d5  retn
0x18000a9d7  sub     rsi, rcx
0x18000a9da  mov     rcx, rsi
0x18000a9dd  shl     rcx, 4; Size
0x18000a9e1  call    cs:__imp_malloc
0x18000a9e8  nop     dword ptr [rax+rax+00h]
0x18000a9ed  mov     r13, rax
0x18000a9f0  test    rax, rax
0x18000a9f3  jz      def_18000AA8A; jumptable 000000018000AA8A default case, cases 69-72,74-82,85-99,103-116,118,119
0x18000a9f9  xor     edi, edi
0x18000a9fb  mov     ebx, edi
0x18000a9fd  lea     rdx, __ImageBase
0x18000aa04  cmp     rbx, rsi
0x18000aa07  jnb     loc_18000A916
0x18000aa0d  movzx   eax, word ptr [r14+rdi*2]
0x18000aa12  mov     r15, r12
0x18000aa15  cmp     eax, 69h ; 'i'
0x18000aa18  jnz     short loc_18000AA6A
0x18000aa1a  mov     ecx, 8; Size
0x18000aa1f  call    cs:__imp_malloc
0x18000aa26  nop     dword ptr [rax+rax+00h]
0x18000aa2b  mov     [rbp+rdi*8+400h+Block], rax
0x18000aa30  test    rax, rax
0x18000aa33  jz      def_18000AA8A; jumptable 000000018000AA8A default case, cases 69-72,74-82,85-99,103-116,118,119
0x18000aa39  mov     r15, [r15]
0x18000aa3c  add     rbx, rbx
0x18000aa3f  mov     [rax], r15
0x18000aa42  add     r12, 8
0x18000aa46  xor     ecx, ecx
0x18000aa48  mov     [r13+rbx*8+0], rax
0x18000aa4d  xor     eax, eax
0x18000aa4f  mov     qword ptr [r13+rbx*8+8], 8
0x18000aa58  lock cmpxchg cs:?_lLoggingEnabled@@3JC, ecx; long volatile _lLoggingEnabled
0x18000aa60  jnz     loc_18000B0F4
0x18000aa66  inc     edi
0x18000aa68  jmp     short loc_18000A9FB
0x18000aa6a  add     eax, 0FFFFFFBCh; switch 53 cases
0x18000aa6d  cmp     eax, 34h
0x18000aa70  ja      def_18000AA8A; jumptable 000000018000AA8A default case, cases 69-72,74-82,85-99,103-116,118,119
0x18000aa76  cdqe
0x18000aa78  movzx   eax, ds:(byte_18000B1C4 - 180000000h)[rdx+rax]
0x18000aa80  mov     ecx, ds:(jpt_18000AA8A - 180000000h)[rdx+rax*4]
0x18000aa87  add     rcx, rdx
0x18000aa8a  jmp     rcx; switch jump
0x18000aa90  mov     r15, [r15]; jumptable 000000018000AA8A case 83
0x18000aa93  lea     rcx, [rbp+400h+DestinationString]; DestinationString
0x18000aa97  xorps   xmm0, xmm0
0x18000aa9a  mov     rdx, r15; SourceString
0x18000aa9d  movups  xmmword ptr [rbp+400h+DestinationString.Length], xmm0
0x18000aaa1  add     r12, 8
0x18000aaa5  call    cs:__imp_RtlInitUnicodeString
0x18000aaac  nop     dword ptr [rax+rax+00h]
0x18000aab1  mov     rax, [rbp+400h+DestinationString.Buffer]
0x18000aab5  add     rbx, rbx
0x18000aab8  xor     ecx, ecx
0x18000aaba  mov     [r13+rbx*8+0], rax
0x18000aabf  movzx   eax, [rbp+400h+DestinationString.Length]
0x18000aac3  add     eax, 2
0x18000aac6  mov     dword ptr [r13+rbx*8+0Ch], 0
0x18000aacf  mov     [r13+rbx*8+8], eax
0x18000aad4  xor     eax, eax
0x18000aad6  lock cmpxchg cs:?_lLoggingEnabled@@3JC, ecx; long volatile _lLoggingEnabled
0x18000aade  jz      short loc_18000AA66
0x18000aae0  mov     rcx, cs:?_pflstate@@3PEAUFileLogState@@EA; FileLogState * _pflstate
0x18000aae7  test    rcx, rcx
0x18000aaea  jz      loc_18000AA66
0x18000aaf0  cmp     byte ptr [rcx+13Bh], 0
0x18000aaf7  jz      loc_18000AA66
0x18000aafd  add     rcx, 50h ; 'P'; Resource
0x18000ab01  mov     dl, 1; Wait
0x18000ab03  call    cs:__imp_RtlAcquireResourceShared
0x18000ab0a  nop     dword ptr [rax+rax+00h]
0x18000ab0f  test    al, al
0x18000ab11  jz      loc_18000AA66
0x18000ab17  mov     rdx, cs:?_pflstate@@3PEAUFileLogState@@EA; FileLogState * _pflstate
0x18000ab1e  xor     bl, bl
0x18000ab20  mov     r8, [rdx+18h]
0x18000ab24  test    r8, r8
0x18000ab27  jz      loc_18000AF41
0x18000ab2d  mov     ecx, [r8]
0x18000ab30  cmp     ecx, 12Eh
0x18000ab36  ja      loc_18000AF41
0x18000ab3c  add     ecx, [r8+4]
0x18000ab40  cmp     ecx, 12Eh
0x18000ab46  ja      loc_18000AF3F
0x18000ab4c  mov     r8, [r8+8]
0x18000ab50  jmp     short loc_18000AB24
0x18000ab52  mov     ecx, 4; jumptable 000000018000AA8A case 100
0x18000ab57  call    cs:__imp_malloc
0x18000ab5e  nop     dword ptr [rax+rax+00h]
0x18000ab63  mov     [rbp+rdi*8+400h+Block], rax
0x18000ab68  test    rax, rax
0x18000ab6b  jz      def_18000AA8A; jumptable 000000018000AA8A default case, cases 69-72,74-82,85-99,103-116,118,119
0x18000ab71  mov     r15d, [r15]
0x18000ab74  add     rbx, rbx
0x18000ab77  mov     [rax], r15d
0x18000ab7a  mov     ecx, 12Eh
0x18000ab7f  add     r12, 8
0x18000ab83  mov     [r13+rbx*8+0], rax
0x18000ab88  mov     qword ptr [r13+rbx*8+8], 4
0x18000ab91  call    FileLogAllowEntry
0x18000ab96  test    al, al
0x18000ab98  jz      loc_18000AA66
0x18000ab9e  mov     edx, r15d
0x18000aba1  lea     rcx, aUint32ParamU; "UINT32 param: %u\n"
0x18000aba8  call    FileLogAppend
0x18000abad  jmp     loc_18000AA66
0x18000abb2  xorps   xmm0, xmm0; jumptable 000000018000AA8A case 84
0x18000abb5  mov     qword ptr [rbp+400h+FileTime.dwLowDateTime], 0
0x18000abbd  mov     ecx, 0C8h; Size
0x18000abc2  movups  xmmword ptr [rbp+400h+SystemTime.wYear], xmm0
0x18000abc6  call    cs:__imp_malloc
0x18000abcd  nop     dword ptr [rax+rax+00h]
0x18000abd2  mov     [rsp+500h+SourceString], rax
0x18000abd7  mov     [rbp+rdi*8+400h+Block], rax
0x18000abdc  test    rax, rax
0x18000abdf  jz      def_18000AA8A; jumptable 000000018000AA8A default case, cases 69-72,74-82,85-99,103-116,118,119
0x18000abe5  mov     rcx, [r15]
0x18000abe8  lea     rdx, [rbp+400h+SystemTime]; lpSystemTime
0x18000abec  mov     qword ptr [rbp+400h+FileTime.dwLowDateTime], rcx
0x18000abf0  add     r12, 8
0x18000abf4  lea     rcx, [rbp+400h+FileTime]; lpFileTime
0x18000abf8  call    cs:__imp_FileTimeToSystemTime
0x18000abff  nop     dword ptr [rax+rax+00h]
0x18000ac04  test    eax, eax
0x18000ac06  jz      loc_18000AF65
0x18000ac0c  movzx   ecx, [rbp+400h+SystemTime.wSecond]
0x18000ac10  movzx   edx, [rbp+400h+SystemTime.wMinute]
0x18000ac14  movzx   r8d, [rbp+400h+SystemTime.wHour]
0x18000ac19  movzx   eax, [rbp+400h+SystemTime.wMilliseconds]
0x18000ac1d  movzx   r10d, [rbp+400h+SystemTime.wDay]
0x18000ac22  movzx   r11d, [rbp+400h+SystemTime.wMonth]
0x18000ac27  movzx   r9d, [rbp+400h+SystemTime.wYear]
0x18000ac2c  mov     dword ptr [rsp+500h+var_4B8.Length], eax
0x18000ac30  mov     dword ptr [rsp+500h+var_4C0], ecx
0x18000ac34  mov     rcx, [rsp+500h+SourceString]; unsigned __int16 *
0x18000ac39  mov     dword ptr [rsp+500h+var_4C8], edx
0x18000ac3d  mov     edx, 64h ; 'd'; unsigned __int64
0x18000ac42  mov     dword ptr [rsp+500h+Arguments], r8d
0x18000ac47  lea     r8, a04u02u02ut02u0; "%04u-%02u-%02uT%02u:%02u:%02u.%uZ"
0x18000ac4e  mov     [rsp+500h+nSize], r10d
0x18000ac53  mov     dword ptr [rsp+500h+lpBuffer], r11d
0x18000ac58  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000ac5d  mov     rdx, [rsp+500h+SourceString]; SourceString
0x18000ac62  lea     rcx, [rsp+500h+var_4B8.Buffer]; DestinationString
0x18000ac67  call    cs:__imp_RtlInitUnicodeString
0x18000ac6e  nop     dword ptr [rax+rax+00h]
0x18000ac73  movzx   ecx, word ptr [rsp+500h+var_4B8.Buffer]
0x18000ac78  add     rbx, rbx
0x18000ac7b  mov     rax, [rsp+500h+var_4A8]
0x18000ac80  add     ecx, 2
0x18000ac83  mov     [r13+rbx*8+8], ecx
0x18000ac88  mov     ecx, 12Eh
0x18000ac8d  mov     [r13+rbx*8+0], rax
0x18000ac92  mov     dword ptr [r13+rbx*8+0Ch], 0
0x18000ac9b  call    FileLogAllowEntry
0x18000aca0  test    al, al
0x18000aca2  jz      loc_18000AA66
0x18000aca8  mov     rdx, [rsp+500h+var_4A8]
0x18000acad  lea     rcx, aSystemtimePara; "SYSTEMTIME param: %s\n"
0x18000acb4  call    FileLogAppend
0x18000acb9  jmp     loc_18000AA66
0x18000acbe  mov     rcx, rdi
0x18000acc1  mov     dword ptr [rsp+500h+lpBuffer], r15d
0x18000acc6  call    CEventWrite
0x18000accb  jmp     def_18000AA8A; jumptable 000000018000AA8A default case, cases 69-72,74-82,85-99,103-116,118,119
0x18000acd0  mov     r15, [r15]; jumptable 000000018000AA8A case 117
0x18000acd3  add     rbx, rbx
0x18000acd6  add     r12, 8
0x18000acda  movzx   ecx, word ptr [r15]
0x18000acde  mov     rax, [r15+8]
0x18000ace2  add     ecx, 2
0x18000ace5  mov     [r13+rbx*8+8], ecx
0x18000acea  mov     ecx, 12Eh
0x18000acef  mov     [r13+rbx*8+0], rax
0x18000acf4  mov     dword ptr [r13+rbx*8+0Ch], 0
0x18000acfd  call    FileLogAllowEntry
0x18000ad02  test    al, al
0x18000ad04  jz      loc_18000AA66
0x18000ad0a  mov     rdx, [r15+8]
0x18000ad0e  lea     rcx, aUnicodestringP; "UnicodeString param: %s\n"
0x18000ad15  jmp     short loc_18000ACB4
0x18000ad17  mov     ecx, 4; jumptable 000000018000AA8A case 68
0x18000ad1c  call    cs:__imp_malloc
0x18000ad23  nop     dword ptr [rax+rax+00h]
0x18000ad28  mov     [rbp+rdi*8+400h+Block], rax
0x18000ad2d  test    rax, rax
0x18000ad30  jz      def_18000AA8A; jumptable 000000018000AA8A default case, cases 69-72,74-82,85-99,103-116,118,119
0x18000ad36  mov     r15d, [r15]
0x18000ad39  add     rbx, rbx
0x18000ad3c  mov     [rax], r15d
0x18000ad3f  mov     ecx, 12Eh
0x18000ad44  add     r12, 8
0x18000ad48  mov     [r13+rbx*8+0], rax
0x18000ad4d  mov     qword ptr [r13+rbx*8+8], 4
0x18000ad56  call    FileLogAllowEntry
0x18000ad5b  test    al, al
0x18000ad5d  jz      loc_18000AA66
0x18000ad63  mov     edx, r15d
0x18000ad66  lea     rcx, aInt32ParamD; "INT32 param: %d\n"
0x18000ad6d  call    FileLogAppend
0x18000ad72  jmp     loc_18000AA66
0x18000ad77  mov     eax, [r12]; jumptable 000000018000AA8A case 101
0x18000ad7b  mov     dword ptr [rsp+500h+SourceString], eax
0x18000ad7f  test    eax, eax
0x18000ad81  jnz     loc_18000AF71
0x18000ad87  mov     r15, cs:g_pwszSuccessMsg
0x18000ad8e  mov     rax, 0FFFFFFFFFFFFFFFFh
  ... truncated ...
```
