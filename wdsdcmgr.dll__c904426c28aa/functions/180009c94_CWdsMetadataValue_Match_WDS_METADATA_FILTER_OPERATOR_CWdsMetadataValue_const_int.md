# CWdsMetadataValue::Match(WDS_METADATA_FILTER_OPERATOR,CWdsMetadataValue const *,int *)

- ea: `0x180009c94`
- end: `0x18000a156`
- name: `?Match@CWdsMetadataValue@@QEBAKW4WDS_METADATA_FILTER_OPERATOR@@PEBV1@PEAH@Z`
- size: `1218`
- prototype: ``
- caller_count: `4`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180009c94`
- `0x18000a54c`
- `0x18000c4e0`
- `0x18000ca00`

## callees

- `0x180009c94`
- `0x1800138dc`
- `0x180014d58`
- `0x180014ee0`
- `0x180015c79`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180009fff`
- `msvcrt!_wcsicmp` at `0x18000a130`
- `msvcrt!_wcsicmp` at `0x180009fff`
- `msvcrt!_wcsicmp` at `0x18000a130`
- `KERNEL32!GetLastError` at `0x180009fb3`
- `KERNEL32!GetLastError` at `0x180009fd6`
- `KERNEL32!GetLastError` at `0x18000a0ca`
- `KERNEL32!GetLastError` at `0x18000a101`
- `KERNEL32!GetLastError` at `0x180009fb3`
- `KERNEL32!GetLastError` at `0x180009fd6`
- `KERNEL32!GetLastError` at `0x18000a0ca`
- `KERNEL32!GetLastError` at `0x18000a101`
- `KERNEL32!SystemTimeToFileTime` at `0x180009fa9`
- `KERNEL32!SystemTimeToFileTime` at `0x180009fcc`
- `KERNEL32!SystemTimeToFileTime` at `0x18000a0c0`
- `KERNEL32!SystemTimeToFileTime` at `0x18000a0f7`
- `KERNEL32!SystemTimeToFileTime` at `0x180009fa9`
- `KERNEL32!SystemTimeToFileTime` at `0x180009fcc`
- `KERNEL32!SystemTimeToFileTime` at `0x18000a0c0`
- `KERNEL32!SystemTimeToFileTime` at `0x18000a0f7`
- `KERNEL32!CompareFileTime` at `0x180009fef`
- `KERNEL32!CompareFileTime` at `0x18000a117`
- `KERNEL32!CompareFileTime` at `0x180009fef`
- `KERNEL32!CompareFileTime` at `0x18000a117`

## pseudocode

```c
__int64 __fastcall CWdsMetadataValue::Match(int *a1, int a2, __int64 a3, DWORD *a4)
{
  int v4; // r10d
  DWORD v5; // ebx
  unsigned int v9; // edi
  int v10; // edx
  int v11; // edx
  int v12; // edx
  int v13; // edx
  int v14; // edx
  int v15; // edx
  const char *v16; // rdx
  DWORD v17; // r12d
  const unsigned __int16 *v18; // rcx
  int v19; // eax
  int v20; // r14d
  bool v21; // zf
  DWORD dwLowDateTime; // r12d
  const unsigned __int16 *v23; // rcx
  int matched; // eax
  unsigned int v25; // eax
  const char *v26; // rdx
  unsigned int v27; // r9d
  const char *v28; // rdx
  const char *v29; // rdx
  const char *v30; // rdx
  const char *v31; // rdx
  int v32; // r10d
  int v33; // r10d
  int v34; // r10d
  __int64 v35; // rax
  bool v36; // zf
  bool v37; // sf
  bool v38; // of
  DWORD LastError; // eax
  const char *v40; // rdx
  unsigned int v41; // r9d
  LONG v42; // eax
  int v43; // r10d
  int v44; // r10d
  int v45; // r10d
  int v46; // r10d
  int v47; // r10d
  int v48; // r10d
  size_t v49; // r8
  int v50; // eax
  __int64 v51; // rax
  FILETIME FileTime2; // [rsp+50h] [rbp+30h] BYREF
  struct _FILETIME FileTime; // [rsp+60h] [rbp+40h] BYREF

  v4 = *a1;
  v5 = 0;
  v9 = 0;
  if ( *a1 != *(_DWORD *)a3 )
  {
    LOBYTE(v5) = a2 == 2;
    *a4 = v5;
    return v9;
  }
  v10 = a2 - 1;
  if ( !v10 )
  {
    v43 = v4 - 1;
    if ( v43 )
    {
      v44 = v43 - 1;
      if ( !v44 )
      {
        v21 = a1[2] == *(_DWORD *)(a3 + 8);
        goto LABEL_81;
      }
      v45 = v44 - 1;
      if ( v45 )
      {
        v46 = v45 - 1;
        if ( v46 )
        {
          v47 = v46 - 1;
          if ( v47 )
          {
            v48 = v47 - 1;
            if ( !v48 )
            {
              v51 = *((_QWORD *)a1 + 1) - *(_QWORD *)(a3 + 8);
              if ( !v51 )
                v51 = *((_QWORD *)a1 + 2) - *(_QWORD *)(a3 + 16);
              v21 = v51 == 0;
              goto LABEL_81;
            }
            if ( v48 != 1 )
              return 13;
            v49 = *((_QWORD *)a1 + 2);
            if ( v49 != *(_QWORD *)(a3 + 16) )
              goto LABEL_82;
            v50 = memcmp_0(*((const void **)a1 + 1), *(const void **)(a3 + 8), v49);
            goto LABEL_80;
          }
        }
        v21 = *((_QWORD *)a1 + 1) == *(_QWORD *)(a3 + 8);
LABEL_81:
        LOBYTE(v5) = v21;
        goto LABEL_82;
      }
      FileTime = 0;
      FileTime2 = 0;
      if ( !SystemTimeToFileTime((const SYSTEMTIME *)(a1 + 2), &FileTime) )
      {
        LastError = GetLastError();
        v41 = 1877;
        goto LABEL_73;
      }
      if ( !SystemTimeToFileTime((const SYSTEMTIME *)(a3 + 8), &FileTime2) )
      {
        LastError = GetLastError();
        v41 = 1882;
LABEL_73:
        v9 = ElValidateWin32(LastError, v40, "base\\eco\\wds\\lib\\metadata\\core\\metadata.cpp", v41);
        if ( !v9 )
          return 31;
        return v9;
      }
      v50 = CompareFileTime(&FileTime, &FileTime2);
    }
    else
    {
      v50 = _wcsicmp(*((const wchar_t **)a1 + 1), *(const wchar_t **)(a3 + 8));
    }
LABEL_80:
    v21 = v50 == 0;
    goto LABEL_81;
  }
  v11 = v10 - 1;
  if ( !v11 )
  {
    FileTime2.dwLowDateTime = 0;
    v25 = CWdsMetadataValue::Match(a1, 1, a3, &FileTime2);
    v27 = 1969;
    goto LABEL_31;
  }
  v12 = v11 - 1;
  if ( !v12 )
  {
    v32 = v4 - 1;
    if ( v32 )
    {
      v33 = v32 - 2;
      if ( v33 )
      {
        v34 = v33 - 1;
        if ( v34 )
        {
          if ( v34 == 1 )
          {
            LOBYTE(v5) = *((_QWORD *)a1 + 1) > *(_QWORD *)(a3 + 8);
            goto LABEL_82;
          }
          return 13;
        }
        v35 = *(_QWORD *)(a3 + 8);
        v38 = __OFSUB__(*((_QWORD *)a1 + 1), v35);
        v36 = *((_QWORD *)a1 + 1) == v35;
        v37 = *((_QWORD *)a1 + 1) - v35 < 0;
LABEL_55:
        LOBYTE(v5) = !(v37 ^ v38 | v36);
        goto LABEL_82;
      }
      FileTime = 0;
      FileTime2 = 0;
      if ( !SystemTimeToFileTime((const SYSTEMTIME *)(a1 + 2), &FileTime) )
      {
        LastError = GetLastError();
        v41 = 1938;
        goto LABEL_73;
      }
      if ( !SystemTimeToFileTime((const SYSTEMTIME *)(a3 + 8), &FileTime2) )
      {
        LastError = GetLastError();
        v41 = 1943;
        goto LABEL_73;
      }
      v42 = CompareFileTime(&FileTime, &FileTime2);
    }
    else
    {
      v42 = _wcsicmp(*((const wchar_t **)a1 + 1), *(const wchar_t **)(a3 + 8));
    }
    v38 = 0;
    v36 = v42 == 0;
    v37 = v42 < 0;
    goto LABEL_55;
  }
  v13 = v12 - 1;
  if ( !v13 )
  {
    FileTime2.dwLowDateTime = 0;
    FileTime.dwLowDateTime = 0;
    v9 = CWdsMetadataValue::Match(a1, 3, a3, &FileTime2);
    if ( ElValidateWin32(v9, v30, "base\\eco\\wds\\lib\\metadata\\core\\metadata.cpp", 0x7BEu) )
      return v9;
    if ( !FileTime2.dwLowDateTime )
    {
      v9 = CWdsMetadataValue::Match(a1, 1, a3, &FileTime);
      if ( ElValidateWin32(v9, v31, "base\\eco\\wds\\lib\\metadata\\core\\metadata.cpp", 0x7C7u) )
        return v9;
      v21 = FileTime.dwLowDateTime == 0;
      goto LABEL_81;
    }
LABEL_82:
    *a4 = v5;
    return v9;
  }
  v14 = v13 - 1;
  if ( !v14 )
  {
    FileTime2.dwLowDateTime = 0;
    FileTime.dwLowDateTime = 0;
    v9 = CWdsMetadataValue::Match(a1, 3, a3, &FileTime2);
    if ( !ElValidateWin32(v9, v28, "base\\eco\\wds\\lib\\metadata\\core\\metadata.cpp", 0x7D4u) )
    {
      if ( FileTime2.dwLowDateTime )
      {
        *a4 = 1;
      }
      else
      {
        v9 = CWdsMetadataValue::Match(a1, 1, a3, &FileTime);
        if ( !ElValidateWin32(v9, v29, "base\\eco\\wds\\lib\\metadata\\core\\metadata.cpp", 0x7DDu) )
          *a4 = FileTime.dwLowDateTime;
      }
    }
    return v9;
  }
  v15 = v14 - 1;
  if ( !v15 )
  {
    FileTime2.dwLowDateTime = 0;
    v25 = CWdsMetadataValue::Match(a1, 3, a3, &FileTime2);
    v27 = 2025;
LABEL_31:
    v9 = v25;
    if ( ElValidateWin32(v25, v26, "base\\eco\\wds\\lib\\metadata\\core\\metadata.cpp", v27) )
      return v9;
    v21 = FileTime2.dwLowDateTime == 0;
    goto LABEL_81;
  }
  v16 = (const char *)(unsigned int)(v15 - 1);
  if ( !(_DWORD)v16 )
  {
    FileTime2.dwLowDateTime = 0;
    dwLowDateTime = 0;
    if ( v4 != 1 )
    {
      v9 = 87;
      if ( ElValidateWin32(0x57u, v16, "base\\eco\\wds\\lib\\metadata\\core\\metadata.cpp", 0x7F8u) )
        return v9;
    }
    v23 = (const unsigned __int16 *)*((_QWORD *)a1 + 1);
    if ( v23 )
    {
      matched = MatchWildcards(v23, *(const unsigned __int16 **)(a3 + 8), (int *)&FileTime2);
      dwLowDateTime = FileTime2.dwLowDateTime;
      v20 = matched;
    }
    else
    {
      v20 = -2147024809;
    }
    if ( (int)ElValidateHr(v20, v16, "base\\eco\\wds\\lib\\metadata\\core\\metadata.cpp", 0x7FEu) >= 0 )
    {
      *a4 = dwLowDateTime;
      return v9;
    }
    goto LABEL_18;
  }
  if ( (_DWORD)v16 != 1 )
    return 87;
  FileTime2.dwLowDateTime = 0;
  v17 = 0;
  if ( v4 == 1 || (v9 = 87, !ElValidateWin32(0x57u, v16, "base\\eco\\wds\\lib\\metadata\\core\\metadata.cpp", 0x80Du)) )
  {
    v18 = (const unsigned __int16 *)*((_QWORD *)a1 + 1);
    if ( v18 )
    {
      v19 = MatchWildcards(v18, *(const unsigned __int16 **)(a3 + 8), (int *)&FileTime2);
      v17 = FileTime2.dwLowDateTime;
      v20 = v19;
    }
    else
    {
      v20 = -2147024809;
    }
    if ( (int)ElValidateHr(v20, v16, "base\\eco\\wds\\lib\\metadata\\core\\metadata.cpp", 0x813u) < 0 )
    {
LABEL_18:
      if ( v20 < 0 && (v20 & 0x1FFF0000) == 0x70000 )
        return (unsigned __int16)v20;
      else
        return (unsigned int)v20;
    }
    v21 = v17 == 0;
    goto LABEL_81;
  }
  return v9;
}

```

## disassembly

```asm
0x180009c94  mov     [rsp-28h+arg_8], rbx
0x180009c99  mov     [rsp-28h+arg_18], rsi
0x180009c9e  push    rbp
0x180009c9f  push    rdi
0x180009ca0  push    r12
0x180009ca2  push    r14
0x180009ca4  push    r15
0x180009ca6  mov     rbp, rsp
0x180009ca9  sub     rsp, 20h
0x180009cad  mov     r10d, [rcx]
0x180009cb0  xor     ebx, ebx
0x180009cb2  mov     rsi, r9
0x180009cb5  mov     r14, r8
0x180009cb8  mov     r15, rcx
0x180009cbb  mov     edi, ebx
0x180009cbd  cmp     r10d, [r8]
0x180009cc0  jz      short loc_180009CD0
0x180009cc2  cmp     edx, 2
0x180009cc5  setz    bl
0x180009cc8  mov     [r9], ebx
0x180009ccb  jmp     loc_18000A13D
0x180009cd0  sub     edx, 1
0x180009cd3  jz      loc_18000A02B
0x180009cd9  sub     edx, 1
0x180009cdc  jz      loc_18000A00F
0x180009ce2  sub     edx, 1
0x180009ce5  jz      loc_180009F5D
0x180009ceb  sub     edx, 1
0x180009cee  jz      loc_180009EEA
0x180009cf4  sub     edx, 1
0x180009cf7  jz      loc_180009E6C
0x180009cfd  sub     edx, 1
0x180009d00  jz      loc_180009E35
0x180009d06  sub     edx, 1; char *
0x180009d09  jz      loc_180009DB6
0x180009d0f  cmp     edx, 1
0x180009d12  jz      short loc_180009D1E
0x180009d14  mov     edi, 57h ; 'W'
0x180009d19  jmp     loc_18000A13D
0x180009d1e  mov     [rbp+FileTime2.dwLowDateTime], ebx
0x180009d21  mov     r12d, ebx
0x180009d24  cmp     r10d, 1
0x180009d28  jz      short loc_180009D4B
0x180009d2a  mov     ecx, 57h ; 'W'; unsigned int
0x180009d2f  lea     r8, aBaseEcoWdsLibM; "base\\eco\\wds\\lib\\metadata\\core\\me"...
0x180009d36  mov     r9d, 80Dh; unsigned int
0x180009d3c  mov     edi, ecx
0x180009d3e  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180009d43  test    eax, eax
0x180009d45  jnz     loc_18000A13D
0x180009d4b  mov     rcx, [r15+8]; unsigned __int16 *
0x180009d4f  test    rcx, rcx
0x180009d52  jz      short loc_180009D6A
0x180009d54  mov     rdx, [r14+8]; unsigned __int16 *
0x180009d58  lea     r8, [rbp+FileTime2]; int *
0x180009d5c  call    ?MatchWildcards@@YAJPEBG0AEAH@Z; MatchWildcards(ushort const *,ushort const *,int &)
0x180009d61  mov     r12d, [rbp+FileTime2.dwLowDateTime]
0x180009d65  mov     r14d, eax
0x180009d68  jmp     short loc_180009D70
0x180009d6a  mov     r14d, 80070057h
0x180009d70  mov     r9d, 813h; unsigned int
0x180009d76  lea     r8, aBaseEcoWdsLibM; "base\\eco\\wds\\lib\\metadata\\core\\me"...
0x180009d7d  mov     ecx, r14d; int
0x180009d80  call    ?ElValidateHr@@YAJJPEBD0K@Z; ElValidateHr(long,char const *,char const *,ulong)
0x180009d85  test    eax, eax
0x180009d87  jns     short loc_180009DAE
0x180009d89  test    r14d, r14d
0x180009d8c  jns     loc_180009E2D
0x180009d92  mov     eax, r14d
0x180009d95  and     eax, 1FFF0000h
0x180009d9a  cmp     eax, 70000h
0x180009d9f  jnz     loc_180009E2D
0x180009da5  movzx   edi, r14w
0x180009da9  jmp     loc_18000A13D
0x180009dae  test    r12d, r12d
0x180009db1  jmp     loc_18000A138
0x180009db6  mov     [rbp+FileTime2.dwLowDateTime], ebx
0x180009db9  mov     r12d, ebx
0x180009dbc  cmp     r10d, 1
0x180009dc0  jz      short loc_180009DE3
0x180009dc2  mov     ecx, 57h ; 'W'; unsigned int
0x180009dc7  lea     r8, aBaseEcoWdsLibM; "base\\eco\\wds\\lib\\metadata\\core\\me"...
0x180009dce  mov     r9d, 7F8h; unsigned int
0x180009dd4  mov     edi, ecx
0x180009dd6  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180009ddb  test    eax, eax
0x180009ddd  jnz     loc_18000A13D
0x180009de3  mov     rcx, [r15+8]; unsigned __int16 *
0x180009de7  test    rcx, rcx
0x180009dea  jz      short loc_180009E02
0x180009dec  mov     rdx, [r14+8]; unsigned __int16 *
0x180009df0  lea     r8, [rbp+FileTime2]; int *
0x180009df4  call    ?MatchWildcards@@YAJPEBG0AEAH@Z; MatchWildcards(ushort const *,ushort const *,int &)
0x180009df9  mov     r12d, [rbp+FileTime2.dwLowDateTime]
0x180009dfd  mov     r14d, eax
0x180009e00  jmp     short loc_180009E08
0x180009e02  mov     r14d, 80070057h
0x180009e08  mov     r9d, 7FEh; unsigned int
0x180009e0e  lea     r8, aBaseEcoWdsLibM; "base\\eco\\wds\\lib\\metadata\\core\\me"...
0x180009e15  mov     ecx, r14d; int
0x180009e18  call    ?ElValidateHr@@YAJJPEBD0K@Z; ElValidateHr(long,char const *,char const *,ulong)
0x180009e1d  test    eax, eax
0x180009e1f  js      loc_180009D89
0x180009e25  mov     [rsi], r12d
0x180009e28  jmp     loc_18000A13D
0x180009e2d  mov     edi, r14d
0x180009e30  jmp     loc_18000A13D
0x180009e35  lea     r9, [rbp+FileTime2]
0x180009e39  mov     [rbp+FileTime2.dwLowDateTime], ebx
0x180009e3c  mov     edx, 3
0x180009e41  call    ?Match@CWdsMetadataValue@@QEBAKW4WDS_METADATA_FILTER_OPERATOR@@PEBV1@PEAH@Z; CWdsMetadataValue::Match(WDS_METADATA_FILTER_OPERATOR,CWdsMetadataValue const *,int *)
0x180009e46  mov     r9d, 7E9h; unsigned int
0x180009e4c  lea     r8, aBaseEcoWdsLibM; "base\\eco\\wds\\lib\\metadata\\core\\me"...
0x180009e53  mov     ecx, eax; unsigned int
0x180009e55  mov     edi, eax
0x180009e57  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180009e5c  test    eax, eax
0x180009e5e  jnz     loc_18000A13D
0x180009e64  cmp     [rbp+FileTime2.dwLowDateTime], ebx
0x180009e67  jmp     loc_18000A138
0x180009e6c  lea     r9, [rbp+FileTime2]
0x180009e70  mov     [rbp+FileTime2.dwLowDateTime], ebx
0x180009e73  mov     edx, 3
0x180009e78  mov     [rbp+FileTime.dwLowDateTime], ebx
0x180009e7b  call    ?Match@CWdsMetadataValue@@QEBAKW4WDS_METADATA_FILTER_OPERATOR@@PEBV1@PEAH@Z; CWdsMetadataValue::Match(WDS_METADATA_FILTER_OPERATOR,CWdsMetadataValue const *,int *)
0x180009e80  mov     edi, eax
0x180009e82  mov     r9d, 7D4h; unsigned int
0x180009e88  lea     r8, aBaseEcoWdsLibM; "base\\eco\\wds\\lib\\metadata\\core\\me"...
0x180009e8f  mov     ecx, eax; unsigned int
0x180009e91  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180009e96  test    eax, eax
0x180009e98  jnz     loc_18000A13D
0x180009e9e  cmp     [rbp+FileTime2.dwLowDateTime], ebx
0x180009ea1  jz      short loc_180009EAE
0x180009ea3  mov     dword ptr [rsi], 1
0x180009ea9  jmp     loc_18000A13D
0x180009eae  lea     r9, [rbp+FileTime]
0x180009eb2  mov     r8, r14
0x180009eb5  mov     edx, 1
0x180009eba  mov     rcx, r15
0x180009ebd  call    ?Match@CWdsMetadataValue@@QEBAKW4WDS_METADATA_FILTER_OPERATOR@@PEBV1@PEAH@Z; CWdsMetadataValue::Match(WDS_METADATA_FILTER_OPERATOR,CWdsMetadataValue const *,int *)
0x180009ec2  mov     edi, eax
0x180009ec4  mov     r9d, 7DDh; unsigned int
0x180009eca  lea     r8, aBaseEcoWdsLibM; "base\\eco\\wds\\lib\\metadata\\core\\me"...
0x180009ed1  mov     ecx, eax; unsigned int
0x180009ed3  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180009ed8  test    eax, eax
0x180009eda  jnz     loc_18000A13D
0x180009ee0  mov     eax, [rbp+FileTime.dwLowDateTime]
0x180009ee3  mov     [rsi], eax
0x180009ee5  jmp     loc_18000A13D
0x180009eea  lea     r9, [rbp+FileTime2]
0x180009eee  mov     [rbp+FileTime2.dwLowDateTime], ebx
0x180009ef1  mov     edx, 3
0x180009ef6  mov     [rbp+FileTime.dwLowDateTime], ebx
0x180009ef9  call    ?Match@CWdsMetadataValue@@QEBAKW4WDS_METADATA_FILTER_OPERATOR@@PEBV1@PEAH@Z; CWdsMetadataValue::Match(WDS_METADATA_FILTER_OPERATOR,CWdsMetadataValue const *,int *)
0x180009efe  mov     edi, eax
0x180009f00  mov     r9d, 7BEh; unsigned int
0x180009f06  lea     r8, aBaseEcoWdsLibM; "base\\eco\\wds\\lib\\metadata\\core\\me"...
0x180009f0d  mov     ecx, eax; unsigned int
0x180009f0f  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180009f14  test    eax, eax
0x180009f16  jnz     loc_18000A13D
0x180009f1c  cmp     [rbp+FileTime2.dwLowDateTime], ebx
0x180009f1f  jnz     loc_18000A13B
0x180009f25  lea     r9, [rbp+FileTime]
0x180009f29  mov     r8, r14
0x180009f2c  lea     edx, [rax+1]
0x180009f2f  mov     rcx, r15
0x180009f32  call    ?Match@CWdsMetadataValue@@QEBAKW4WDS_METADATA_FILTER_OPERATOR@@PEBV1@PEAH@Z; CWdsMetadataValue::Match(WDS_METADATA_FILTER_OPERATOR,CWdsMetadataValue const *,int *)
0x180009f37  mov     edi, eax
0x180009f39  mov     r9d, 7C7h; unsigned int
0x180009f3f  lea     r8, aBaseEcoWdsLibM; "base\\eco\\wds\\lib\\metadata\\core\\me"...
0x180009f46  mov     ecx, eax; unsigned int
0x180009f48  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180009f4d  test    eax, eax
0x180009f4f  jnz     loc_18000A13D
0x180009f55  cmp     [rbp+FileTime.dwLowDateTime], ebx
0x180009f58  jmp     loc_18000A138
0x180009f5d  sub     r10d, 1
0x180009f61  jz      loc_180009FF7
0x180009f67  sub     r10d, 2
0x180009f6b  jz      short loc_180009F97
0x180009f6d  sub     r10d, 1
0x180009f71  jz      short loc_180009F8D
0x180009f73  cmp     r10d, 1
0x180009f77  jnz     loc_18000A05D
0x180009f7d  mov     rax, [r8+8]
0x180009f81  cmp     [rcx+8], rax
0x180009f85  setnbe  bl
0x180009f88  jmp     loc_18000A13B
0x180009f8d  mov     rax, [r8+8]
0x180009f91  cmp     [rcx+8], rax
0x180009f95  jmp     short loc_18000A007
0x180009f97  xor     eax, eax
0x180009f99  lea     rdx, [rbp+FileTime]; lpFileTime
0x180009f9d  add     rcx, 8; lpSystemTime
0x180009fa1  mov     qword ptr [rbp+FileTime.dwLowDateTime], rax
0x180009fa5  mov     qword ptr [rbp+FileTime2.dwLowDateTime], rax
0x180009fa9  call    cs:__imp_SystemTimeToFileTime
0x180009faf  test    eax, eax
0x180009fb1  jnz     short loc_180009FC4
0x180009fb3  call    cs:__imp_GetLastError
0x180009fb9  mov     r9d, 792h
0x180009fbf  jmp     loc_18000A0D6
0x180009fc4  lea     rcx, [r14+8]; lpSystemTime
0x180009fc8  lea     rdx, [rbp+FileTime2]; lpFileTime
0x180009fcc  call    cs:__imp_SystemTimeToFileTime
0x180009fd2  test    eax, eax
0x180009fd4  jnz     short loc_180009FE7
0x180009fd6  call    cs:__imp_GetLastError
0x180009fdc  mov     r9d, 797h
0x180009fe2  jmp     loc_18000A0D6
0x180009fe7  lea     rdx, [rbp+FileTime2]; lpFileTime2
0x180009feb  lea     rcx, [rbp+FileTime]; lpFileTime1
0x180009fef  call    cs:__imp_CompareFileTime
0x180009ff5  jmp     short loc_18000A005
0x180009ff7  mov     rdx, [r8+8]; String2
0x180009ffb  mov     rcx, [rcx+8]; String1
0x180009fff  call    cs:__imp__wcsicmp
0x18000a005  test    eax, eax
0x18000a007  setnle  bl
0x18000a00a  jmp     loc_18000A13B
0x18000a00f  lea     r9, [rbp+FileTime2]
0x18000a013  mov     [rbp+FileTime2.dwLowDateTime], ebx
0x18000a016  mov     edx, 1
0x18000a01b  call    ?Match@CWdsMetadataValue@@QEBAKW4WDS_METADATA_FILTER_OPERATOR@@PEBV1@PEAH@Z; CWdsMetadataValue::Match(WDS_METADATA_FILTER_OPERATOR,CWdsMetadataValue const *,int *)
0x18000a020  mov     r9d, 7B1h
0x18000a026  jmp     loc_180009E4C
0x18000a02b  sub     r10d, 1
0x18000a02f  jz      loc_18000A128
0x18000a035  sub     r10d, 1
0x18000a039  jz      loc_18000A11F
0x18000a03f  sub     r10d, 1
0x18000a043  jz      short loc_18000A0AE
0x18000a045  sub     r10d, 1
0x18000a049  jz      short loc_18000A0A1
0x18000a04b  sub     r10d, 1
0x18000a04f  jz      short loc_18000A0A1
0x18000a051  sub     r10d, 1
0x18000a055  jz      short loc_18000A087
0x18000a057  cmp     r10d, 1
0x18000a05b  jz      short loc_18000A067
0x18000a05d  mov     edi, 0Dh
0x18000a062  jmp     loc_18000A13D
0x18000a067  mov     r8, [rcx+10h]; Size
0x18000a06b  cmp     r8, [r14+10h]
0x18000a06f  jnz     loc_18000A13B
0x18000a075  mov     rdx, [r14+8]; Buf2
0x18000a079  mov     rcx, [rcx+8]; Buf1
0x18000a07d  call    memcmp_0
0x18000a082  jmp     loc_18000A136
0x18000a087  mov     rax, [rcx+8]
0x18000a08b  sub     rax, [r8+8]
0x18000a08f  jnz     short loc_18000A099
0x18000a091  mov     rax, [rcx+10h]
0x18000a095  sub     rax, [r8+10h]
0x18000a099  test    rax, rax
0x18000a09c  jmp     loc_18000A138
0x18000a0a1  mov     rax, [r8+8]
0x18000a0a5  cmp     [rcx+8], rax
0x18000a0a9  jmp     loc_18000A138
0x18000a0ae  xor     eax, eax
0x18000a0b0  lea     rdx, [rbp+FileTime]; lpFileTime
0x18000a0b4  add     rcx, 8; lpSystemTime
0x18000a0b8  mov     qword ptr [rbp+FileTime.dwLowDateTime], rax
0x18000a0bc  mov     qword ptr [rbp+FileTime2.dwLowDateTime], rax
0x18000a0c0  call    cs:__imp_SystemTimeToFileTime
0x18000a0c6  test    eax, eax
0x18000a0c8  jnz     short loc_18000A0EF
0x18000a0ca  call    cs:__imp_GetLastError
0x18000a0d0  mov     r9d, 755h; unsigned int
0x18000a0d6  mov     ecx, eax; unsigned int
0x18000a0d8  lea     r8, aBaseEcoWdsLibM; "base\\eco\\wds\\lib\\metadata\\core\\me"...
0x18000a0df  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18000a0e4  mov     edi, eax
0x18000a0e6  test    eax, eax
0x18000a0e8  jnz     short loc_18000A13D
0x18000a0ea  lea     edi, [rax+1Fh]
0x18000a0ed  jmp     short loc_18000A13D
0x18000a0ef  lea     rcx, [r14+8]; lpSystemTime
0x18000a0f3  lea     rdx, [rbp+FileTime2]; lpFileTime
0x18000a0f7  call    cs:__imp_SystemTimeToFileTime
0x18000a0fd  test    eax, eax
0x18000a0ff  jnz     short loc_18000A10F
0x18000a101  call    cs:__imp_GetLastError
0x18000a107  mov     r9d, 75Ah
0x18000a10d  jmp     short loc_18000A0D6
0x18000a10f  lea     rdx, [rbp+FileTime2]; lpFileTime2
0x18000a113  lea     rcx, [rbp+FileTime]; lpFileTime1
0x18000a117  call    cs:__imp_CompareFileTime
0x18000a11d  jmp     short loc_18000A136
0x18000a11f  mov     eax, [r8+8]
0x18000a123  cmp     [rcx+8], eax
0x18000a126  jmp     short loc_18000A138
0x18000a128  mov     rdx, [r8+8]; String2
0x18000a12c  mov     rcx, [rcx+8]; String1
0x18000a130  call    cs:__imp__wcsicmp
0x18000a136  test    eax, eax
0x18000a138  setz    bl
  ... truncated ...
```
