# NgscbpCheckIsHSTIVerified

- ea: `0x1800380a4`
- end: `0x18003870c`
- name: `NgscbpCheckIsHSTIVerified`
- size: `1640`
- prototype: `__int64 __fastcall(bool *)`
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180036ee0`

## callees

- `0x180021ec0`
- `0x180022a10`
- `0x180036dcc`
- `0x180036ebc`
- `0x180036f9c`
- `0x1800380a4`
- `0x1800389b8`
- `0x180038c08`
- `0x180038d4c`
- `0x180038de0`
- `0x180038e84`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800386d7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800386d7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800386c9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800386c9`
- `ntdll!NtQuerySystemInformation` at `0x180038168`
- `ntdll!NtQuerySystemInformation` at `0x18003843b`
- `ntdll!NtQuerySystemInformation` at `0x180038168`
- `ntdll!NtQuerySystemInformation` at `0x18003843b`

## string_xrefs

- `0x1800381a2`: `ngscb_common_um`
- `0x180038242`: `ngscb_common_um`
- `0x1800382de`: `ngscb_common_um`
- `0x18003830b`: `ngscb_common_um`

## pseudocode

```c
__int64 __fastcall NgscbpCheckIsHSTIVerified(bool *a1, struct _NGSCB_HSTI_RESULTS **a2)
{
  int v4; // r14d
  _QWORD *v5; // rcx
  __int64 v6; // rdx
  __int64 v7; // r9
  unsigned int v8; // eax
  __int64 v9; // rbx
  __int64 v10; // rbx
  unsigned int v11; // eax
  __int64 v12; // rbx
  __int64 v13; // rax
  unsigned int v14; // eax
  NTSTATUS v15; // eax
  unsigned int v16; // eax
  _BYTE *v17; // rcx
  __int64 v18; // rdx
  __int64 v19; // rax
  __int64 v20; // r9
  _DWORD *v21; // r13
  PVOID v22; // rdi
  HANDLE ProcessHeap; // rax
  ULONG ReturnLength; // [rsp+30h] [rbp-59h] BYREF
  int v26; // [rsp+34h] [rbp-55h] BYREF
  ULONG v27; // [rsp+38h] [rbp-51h] BYREF
  PVOID SystemInformation; // [rsp+40h] [rbp-49h] BYREF
  struct _NGSCB_HSTI_RESULTS **v29; // [rsp+48h] [rbp-41h]
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+50h] [rbp-39h] BYREF
  ULONG *v31; // [rsp+60h] [rbp-29h]
  __int64 v32; // [rsp+68h] [rbp-21h]
  wchar_t *v33; // [rsp+70h] [rbp-19h]
  int v34; // [rsp+78h] [rbp-11h]
  int v35; // [rsp+7Ch] [rbp-Dh]

  v29 = a2;
  v26 = 0;
  SystemInformation = 0;
  ReturnLength = 0;
  v27 = 0;
  UserData.Ptr = 0;
  memset_0(&UserData.Size, 0, 0x48u);
  if ( a2 )
    *a2 = 0;
  if ( !a1 )
  {
    v4 = -2147467261;
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    {
      v6 = 30;
      v7 = 2147500035LL;
LABEL_7:
      WPP_SF_d(v5[2], v6, &WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids, v7);
      goto LABEL_88;
    }
    goto LABEL_88;
  }
  v4 = 0;
  *a1 = 0;
  NgscbTryOpenEventLog();
  v8 = NtQuerySystemInformation(SystemExtendServiceTableInformation|0x80, 0, 0, &ReturnLength);
  v26 = v8;
  if ( v8 == -1073741275 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 31);
    v9 = -1;
    UserData.Ptr = (ULONGLONG)aNgscbCommonUm;
    do
      ++v9;
    while ( aNgscbCommonUm[v9] );
LABEL_14:
    UserData.Reserved = 0;
    UserData.Size = 2 * v9 + 2;
    NgscbTryWriteEventLog(&FVE_AUTODE_HSTI_NOT_SUPPORTED, 1u, &UserData);
    goto LABEL_88;
  }
  if ( (int)(v8 + 0x80000000) < 0 || v8 == -1073741820 )
  {
    if ( !ReturnLength )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 34);
      v9 = -1;
      UserData.Ptr = (ULONGLONG)aNgscbCommonUm;
      do
        ++v9;
      while ( aNgscbCommonUm[v9] );
      goto LABEL_14;
    }
    v27 = 8;
    UserData.Ptr = (ULONGLONG)&ReturnLength;
    *(_QWORD *)&UserData.Size = 4;
    v12 = -1;
    v31 = &v27;
    v13 = -1;
    v32 = 4;
    v33 = aNgscbCommonUm;
    do
      ++v13;
    while ( aNgscbCommonUm[v13] );
    v35 = 0;
    v34 = 2 * v13 + 2;
    NgscbTryWriteEventLog(&FVE_AUTODE_HSTI_REPORT_DATA_SIZE, 3u, &UserData);
    if ( ReturnLength < v27 )
    {
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          35,
          &WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids,
          ReturnLength);
        v5 = WPP_GLOBAL_Control;
      }
      v7 = 2147942413LL;
      v4 = -2147024883;
      if ( v5 != &WPP_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 0x40) != 0 )
      {
        v6 = 36;
        goto LABEL_7;
      }
      goto LABEL_88;
    }
    v14 = HeapAllocateByByteCount<unsigned char>(&SystemInformation, ReturnLength);
    v4 = v14;
    if ( !v14 )
      goto LABEL_46;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, &WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids, v14);
    if ( v4 >= 0 )
    {
LABEL_46:
      memset_0(SystemInformation, 0, ReturnLength);
      v15 = NtQuerySystemInformation(
              SystemExtendServiceTableInformation|0x80,
              SystemInformation,
              ReturnLength,
              &ReturnLength);
      v26 = v15;
      if ( v15 < 0 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            38,
            &WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids,
            (unsigned int)v15);
        *(_QWORD *)&UserData.Size = 4;
        UserData.Ptr = (ULONGLONG)&v26;
        v31 = (ULONG *)aNgscbCommonUm;
        do
          ++v12;
        while ( aNgscbCommonUm[v12] );
        v32 = (unsigned int)(2 * v12 + 2);
        NgscbTryWriteEventLog(&FVE_AUTODE_HSTI_QUERY_FAILED, 2u, &UserData);
        v16 = FromNtStatus(v26);
        v4 = v16;
        v17 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 )
          goto LABEL_86;
        v18 = 39;
        goto LABEL_84;
      }
      *(_QWORD *)&UserData.Size = 4;
      UserData.Ptr = (ULONGLONG)&ReturnLength;
      v31 = &v27;
      v19 = -1;
      v32 = 4;
      v33 = aNgscbCommonUm;
      do
        ++v19;
      while ( aNgscbCommonUm[v19] );
      v35 = 0;
      v34 = 2 * v19 + 2;
      NgscbTryWriteEventLog(&FVE_AUTODE_HSTI_REPORT_DATA_SIZE, 3u, &UserData);
      if ( ReturnLength < v27 )
      {
        v17 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            40,
            &WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids,
            ReturnLength);
          v17 = WPP_GLOBAL_Control;
        }
        v20 = 2147942413LL;
        v4 = -2147024883;
        if ( v17 == (_BYTE *)&WPP_GLOBAL_Control || (v17[28] & 0x40) == 0 )
          goto LABEL_86;
        v18 = 41;
        goto LABEL_85;
      }
      if ( ReturnLength >= 0x14 )
      {
        v16 = NgscbCheckParseHSTIResults((unsigned __int8 *)SystemInformation, ReturnLength, a1, v29);
        v4 = v16;
        if ( v16 )
        {
          v17 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
          {
            v18 = 46;
LABEL_84:
            v20 = v16;
            goto LABEL_85;
          }
        }
      }
      else
      {
        v21 = (char *)SystemInformation + 4;
        *(_QWORD *)&UserData.Size = 4;
        UserData.Ptr = (ULONGLONG)SystemInformation + 4;
        v31 = (ULONG *)aNgscbCommonUm;
        do
          ++v12;
        while ( aNgscbCommonUm[v12] );
        v32 = (unsigned int)(2 * v12 + 2);
        NgscbTryWriteEventLog(&FVE_AUTODE_HSTI_REPORT_PROVIDER_COUNT, 2u, &UserData);
        if ( !*v21 )
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 45);
          goto LABEL_86;
        }
        v17 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
        {
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              42,
              &WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids,
              ReturnLength);
            v17 = WPP_GLOBAL_Control;
          }
          if ( v17 != (_BYTE *)&WPP_GLOBAL_Control && (v17[28] & 2) != 0 )
          {
            WPP_SF_d(*((_QWORD *)v17 + 2), 43, &WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids, (unsigned int)*v21);
            v17 = WPP_GLOBAL_Control;
          }
        }
        v20 = 2147942413LL;
        v4 = -2147024883;
        if ( v17 != (_BYTE *)&WPP_GLOBAL_Control && (v17[28] & 0x40) != 0 )
        {
          v18 = 44;
LABEL_85:
          WPP_SF_d(*((_QWORD *)v17 + 2), v18, &WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids, v20);
        }
      }
    }
LABEL_86:
    v22 = SystemInformation;
    if ( SystemInformation )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v22);
    }
    goto LABEL_88;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, &WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids, v8);
  *(_QWORD *)&UserData.Size = 4;
  UserData.Ptr = (ULONGLONG)&v26;
  v10 = -1;
  v31 = (ULONG *)aNgscbCommonUm;
  do
    ++v10;
  while ( aNgscbCommonUm[v10] );
  v32 = (unsigned int)(2 * v10 + 2);
  NgscbTryWriteEventLog(&FVE_AUTODE_HSTI_QUERY_FAILED, 2u, &UserData);
  v11 = FromNtStatus(v26);
  v4 = v11;
  v5 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
  {
    v6 = 33;
    v7 = v11;
    goto LABEL_7;
  }
LABEL_88:
  NgscbTryCloseEventLog();
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800380a4  mov     [rsp-8+arg_10], rbx
0x1800380a9  push    rbp
0x1800380aa  push    rsi
0x1800380ab  push    rdi
0x1800380ac  push    r12
0x1800380ae  push    r13
0x1800380b0  push    r14
0x1800380b2  push    r15
0x1800380b4  lea     rbp, [rsp-27h]
0x1800380b9  sub     rsp, 0B0h
0x1800380c0  mov     rax, cs:__security_cookie
0x1800380c7  xor     rax, rsp
0x1800380ca  mov     [rbp+57h+var_40], rax
0x1800380ce  xor     r15d, r15d
0x1800380d1  mov     [rbp+57h+var_98], rdx
0x1800380d5  mov     rbx, rdx
0x1800380d8  mov     [rbp+57h+var_AC], r15d
0x1800380dc  mov     r13, rcx
0x1800380df  mov     [rbp+57h+SystemInformation], r15
0x1800380e3  xor     edx, edx; Val
0x1800380e5  mov     [rbp+57h+ReturnLength], r15d
0x1800380e9  lea     r8d, [r15+48h]; Size
0x1800380ed  mov     [rbp+57h+var_A8], r15d
0x1800380f1  lea     rcx, [rbp+57h+UserData.Size]; void *
0x1800380f5  mov     [rbp+57h+UserData.Ptr], r15
0x1800380f9  call    memset_0
0x1800380fe  test    rbx, rbx
0x180038101  jz      short loc_180038106
0x180038103  mov     [rbx], r15
0x180038106  test    r13, r13
0x180038109  jnz     short loc_18003814E
0x18003810b  mov     r14d, 80004003h
0x180038111  mov     rcx, cs:WPP_GLOBAL_Control
0x180038118  lea     rdi, WPP_GLOBAL_Control
0x18003811f  cmp     rcx, rdi
0x180038122  jz      loc_1800386DD
0x180038128  test    byte ptr [rcx+1Ch], 40h
0x18003812c  jz      loc_1800386DD
0x180038132  lea     edx, [r13+1Eh]
0x180038136  mov     r9d, r14d
0x180038139  lea     r8, WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids
0x180038140  mov     rcx, [rcx+10h]
0x180038144  call    WPP_SF_d
0x180038149  jmp     loc_1800386DD
0x18003814e  mov     r14d, r15d
0x180038151  mov     [r13+0], r15b
0x180038155  call    ?NgscbTryOpenEventLog@@YAXXZ; NgscbTryOpenEventLog(void)
0x18003815a  lea     r9, [rbp+57h+ReturnLength]; ReturnLength
0x18003815e  xor     r8d, r8d; SystemInformationLength
0x180038161  xor     edx, edx; SystemInformation
0x180038163  mov     ecx, 0A6h; SystemInformationClass
0x180038168  call    cs:__imp_NtQuerySystemInformation
0x18003816e  mov     [rbp+57h+var_AC], eax
0x180038171  mov     r9d, eax
0x180038174  cmp     eax, 0C0000225h
0x180038179  jnz     short loc_1800381E3
0x18003817b  mov     rcx, cs:WPP_GLOBAL_Control
0x180038182  lea     rdi, WPP_GLOBAL_Control
0x180038189  cmp     rcx, rdi
0x18003818c  jz      short loc_1800381A2
0x18003818e  test    byte ptr [rcx+1Ch], 8
0x180038192  jz      short loc_1800381A2
0x180038194  mov     rcx, [rcx+10h]
0x180038198  mov     edx, 1Fh
0x18003819d  call    WPP_SF_
0x1800381a2  lea     rsi, aNgscbCommonUm; "ngscb_common_um"
0x1800381a9  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800381ad  mov     [rbp+57h+UserData.Ptr], rsi
0x1800381b1  inc     rbx
0x1800381b4  cmp     [rsi+rbx*2], r15w
0x1800381b9  jnz     short loc_1800381B1
0x1800381bb  lea     eax, ds:2[rbx*2]
0x1800381c2  mov     dword ptr [rbp+57h+UserData.0Ch], r15d
0x1800381c6  lea     r8, [rbp+57h+UserData]; UserData
0x1800381ca  mov     [rbp+57h+UserData.Size], eax
0x1800381cd  mov     edx, 1; UserDataCount
0x1800381d2  lea     rcx, FVE_AUTODE_HSTI_NOT_SUPPORTED; EventDescriptor
0x1800381d9  call    ?NgscbTryWriteEventLog@@YAXPEBU_EVENT_DESCRIPTOR@@KPEAU_EVENT_DATA_DESCRIPTOR@@@Z; NgscbTryWriteEventLog(_EVENT_DESCRIPTOR const *,ulong,_EVENT_DATA_DESCRIPTOR *)
0x1800381de  jmp     loc_1800386DD
0x1800381e3  mov     ecx, 80000000h
0x1800381e8  add     eax, ecx
0x1800381ea  test    ecx, eax
0x1800381ec  jnz     loc_1800382B1
0x1800381f2  cmp     r9d, 0C0000004h
0x1800381f9  jz      loc_1800382B1
0x1800381ff  mov     rcx, cs:WPP_GLOBAL_Control
0x180038206  lea     rdi, WPP_GLOBAL_Control
0x18003820d  lea     r15, WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids
0x180038214  cmp     rcx, rdi
0x180038217  jz      short loc_180038230
0x180038219  test    byte ptr [rcx+1Ch], 2
0x18003821d  jz      short loc_180038230
0x18003821f  mov     rcx, [rcx+10h]
0x180038223  mov     edx, 20h ; ' '
0x180038228  mov     r8, r15
0x18003822b  call    WPP_SF_d
0x180038230  lea     rax, [rbp+57h+var_AC]
0x180038234  mov     qword ptr [rbp+57h+UserData.Size], 4
0x18003823c  xor     ecx, ecx
0x18003823e  mov     [rbp+57h+UserData.Ptr], rax
0x180038242  lea     rsi, aNgscbCommonUm; "ngscb_common_um"
0x180038249  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18003824d  mov     [rbp+57h+var_80], rsi
0x180038251  inc     rbx
0x180038254  cmp     [rsi+rbx*2], cx
0x180038258  jnz     short loc_180038251
0x18003825a  lea     eax, ds:2[rbx*2]
0x180038261  mov     dword ptr [rbp+57h+var_78+4], ecx
0x180038264  lea     rcx, FVE_AUTODE_HSTI_QUERY_FAILED; EventDescriptor
0x18003826b  mov     dword ptr [rbp+57h+var_78], eax
0x18003826e  lea     r8, [rbp+57h+UserData]; UserData
0x180038272  mov     edx, 2; UserDataCount
0x180038277  call    ?NgscbTryWriteEventLog@@YAXPEBU_EVENT_DESCRIPTOR@@KPEAU_EVENT_DATA_DESCRIPTOR@@@Z; NgscbTryWriteEventLog(_EVENT_DESCRIPTOR const *,ulong,_EVENT_DATA_DESCRIPTOR *)
0x18003827c  mov     ecx, [rbp+57h+var_AC]; int
0x18003827f  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x180038284  mov     r14d, eax
0x180038287  mov     rcx, cs:WPP_GLOBAL_Control
0x18003828e  cmp     rcx, rdi
0x180038291  jz      loc_1800386DD
0x180038297  test    byte ptr [rcx+1Ch], 40h
0x18003829b  jz      loc_1800386DD
0x1800382a1  mov     edx, 21h ; '!'
0x1800382a6  mov     r9d, eax
0x1800382a9  mov     r8, r15
0x1800382ac  jmp     loc_180038140
0x1800382b1  cmp     [rbp+57h+ReturnLength], r15d
0x1800382b5  jnz     short loc_1800382FC
0x1800382b7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800382be  lea     rdi, WPP_GLOBAL_Control
0x1800382c5  cmp     rcx, rdi
0x1800382c8  jz      short loc_1800382DE
0x1800382ca  test    byte ptr [rcx+1Ch], 8
0x1800382ce  jz      short loc_1800382DE
0x1800382d0  mov     rcx, [rcx+10h]
0x1800382d4  mov     edx, 22h ; '"'
0x1800382d9  call    WPP_SF_
0x1800382de  lea     rsi, aNgscbCommonUm; "ngscb_common_um"
0x1800382e5  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800382e9  mov     [rbp+57h+UserData.Ptr], rsi
0x1800382ed  inc     rbx
0x1800382f0  cmp     [rsi+rbx*2], r15w
0x1800382f5  jnz     short loc_1800382ED
0x1800382f7  jmp     loc_1800381BB
0x1800382fc  lea     rax, [rbp+57h+ReturnLength]
0x180038300  mov     [rbp+57h+var_A8], 8
0x180038307  mov     [rbp+57h+UserData.Ptr], rax
0x18003830b  lea     rsi, aNgscbCommonUm; "ngscb_common_um"
0x180038312  lea     rax, [rbp+57h+var_A8]
0x180038316  mov     qword ptr [rbp+57h+UserData.Size], 4
0x18003831e  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180038322  mov     [rbp+57h+var_80], rax
0x180038326  mov     rax, rbx
0x180038329  mov     [rbp+57h+var_78], 4
0x180038331  mov     [rbp+57h+var_70], rsi
0x180038335  inc     rax
0x180038338  cmp     [rsi+rax*2], r15w
0x18003833d  jnz     short loc_180038335
0x18003833f  lea     eax, ds:2[rax*2]
0x180038346  mov     [rbp+57h+var_64], r15d
0x18003834a  lea     r8, [rbp+57h+UserData]; UserData
0x18003834e  mov     [rbp+57h+var_68], eax
0x180038351  mov     edx, 3; UserDataCount
0x180038356  lea     rcx, FVE_AUTODE_HSTI_REPORT_DATA_SIZE; EventDescriptor
0x18003835d  call    ?NgscbTryWriteEventLog@@YAXPEBU_EVENT_DESCRIPTOR@@KPEAU_EVENT_DATA_DESCRIPTOR@@@Z; NgscbTryWriteEventLog(_EVENT_DESCRIPTOR const *,ulong,_EVENT_DATA_DESCRIPTOR *)
0x180038362  mov     eax, [rbp+57h+ReturnLength]
0x180038365  cmp     eax, [rbp+57h+var_A8]
0x180038368  jnb     short loc_1800383CB
0x18003836a  mov     rcx, cs:WPP_GLOBAL_Control
0x180038371  lea     rdi, WPP_GLOBAL_Control
0x180038378  lea     r15, WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids
0x18003837f  cmp     rcx, rdi
0x180038382  jz      short loc_1800383A5
0x180038384  test    byte ptr [rcx+1Ch], 2
0x180038388  jz      short loc_1800383A5
0x18003838a  mov     rcx, [rcx+10h]
0x18003838e  mov     edx, 23h ; '#'
0x180038393  mov     r9d, eax
0x180038396  mov     r8, r15
0x180038399  call    WPP_SF_d
0x18003839e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800383a5  mov     r9d, 8007000Dh
0x1800383ab  mov     r14d, r9d
0x1800383ae  cmp     rcx, rdi
0x1800383b1  jz      loc_1800386DD
0x1800383b7  test    byte ptr [rcx+1Ch], 40h
0x1800383bb  jz      loc_1800386DD
0x1800383c1  mov     edx, 24h ; '$'
0x1800383c6  jmp     loc_1800382A9
0x1800383cb  mov     rdx, rax
0x1800383ce  lea     rcx, [rbp+57h+SystemInformation]
0x1800383d2  call    ??$HeapAllocateByByteCount@E@@YAJPEAPEAE_K@Z; HeapAllocateByByteCount<uchar>(uchar * *,unsigned __int64)
0x1800383d7  lea     rdi, WPP_GLOBAL_Control
0x1800383de  mov     r14d, eax
0x1800383e1  lea     r15, WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids
0x1800383e8  test    eax, eax
0x1800383ea  jz      short loc_18003841B
0x1800383ec  mov     rcx, cs:WPP_GLOBAL_Control
0x1800383f3  cmp     rcx, rdi
0x1800383f6  jz      short loc_180038412
0x1800383f8  test    byte ptr [rcx+1Ch], 40h
0x1800383fc  jz      short loc_180038412
0x1800383fe  mov     rcx, [rcx+10h]
0x180038402  mov     edx, 25h ; '%'
0x180038407  mov     r9d, eax
0x18003840a  mov     r8, r15
0x18003840d  call    WPP_SF_d
0x180038412  test    r14d, r14d
0x180038415  js      loc_1800386C0
0x18003841b  mov     r8d, [rbp+57h+ReturnLength]; Size
0x18003841f  xor     edx, edx; Val
0x180038421  mov     rcx, [rbp+57h+SystemInformation]; void *
0x180038425  call    memset_0
0x18003842a  mov     r8d, [rbp+57h+ReturnLength]; SystemInformationLength
0x18003842e  lea     r9, [rbp+57h+ReturnLength]; ReturnLength
0x180038432  mov     rdx, [rbp+57h+SystemInformation]; SystemInformation
0x180038436  mov     ecx, 0A6h; SystemInformationClass
0x18003843b  call    cs:__imp_NtQuerySystemInformation
0x180038441  xor     edx, edx
0x180038443  mov     [rbp+57h+var_AC], eax
0x180038446  test    eax, eax
0x180038448  jns     loc_1800384E4
0x18003844e  mov     rcx, cs:WPP_GLOBAL_Control
0x180038455  cmp     rcx, rdi
0x180038458  jz      short loc_180038476
0x18003845a  test    byte ptr [rcx+1Ch], 2
0x18003845e  jz      short loc_180038476
0x180038460  mov     rcx, [rcx+10h]
0x180038464  mov     edx, 26h ; '&'
0x180038469  mov     r9d, eax
0x18003846c  mov     r8, r15
0x18003846f  call    WPP_SF_d
0x180038474  xor     edx, edx
0x180038476  lea     rax, [rbp+57h+var_AC]
0x18003847a  mov     qword ptr [rbp+57h+UserData.Size], 4
0x180038482  mov     [rbp+57h+UserData.Ptr], rax
0x180038486  mov     [rbp+57h+var_80], rsi
0x18003848a  inc     rbx
0x18003848d  cmp     [rsi+rbx*2], dx
0x180038491  jnz     short loc_18003848A
0x180038493  lea     eax, ds:2[rbx*2]
0x18003849a  mov     dword ptr [rbp+57h+var_78+4], edx
0x18003849d  mov     edx, 2; UserDataCount
0x1800384a2  mov     dword ptr [rbp+57h+var_78], eax
0x1800384a5  lea     r8, [rbp+57h+UserData]; UserData
0x1800384a9  lea     rcx, FVE_AUTODE_HSTI_QUERY_FAILED; EventDescriptor
0x1800384b0  call    ?NgscbTryWriteEventLog@@YAXPEBU_EVENT_DESCRIPTOR@@KPEAU_EVENT_DATA_DESCRIPTOR@@@Z; NgscbTryWriteEventLog(_EVENT_DESCRIPTOR const *,ulong,_EVENT_DATA_DESCRIPTOR *)
0x1800384b5  mov     ecx, [rbp+57h+var_AC]; int
0x1800384b8  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x1800384bd  mov     r14d, eax
0x1800384c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800384c7  cmp     rcx, rdi
0x1800384ca  jz      loc_1800386C0
0x1800384d0  test    byte ptr [rcx+1Ch], 40h
0x1800384d4  jz      loc_1800386C0
0x1800384da  mov     edx, 27h ; '''
0x1800384df  jmp     loc_1800386B1
0x1800384e4  lea     rax, [rbp+57h+ReturnLength]
0x1800384e8  mov     qword ptr [rbp+57h+UserData.Size], 4
0x1800384f0  mov     [rbp+57h+UserData.Ptr], rax
0x1800384f4  lea     rax, [rbp+57h+var_A8]
0x1800384f8  mov     [rbp+57h+var_80], rax
0x1800384fc  mov     rax, rbx
0x1800384ff  mov     [rbp+57h+var_78], 4
0x180038507  mov     [rbp+57h+var_70], rsi
0x18003850b  inc     rax
0x18003850e  cmp     [rsi+rax*2], dx
0x180038512  jnz     short loc_18003850B
0x180038514  lea     eax, ds:2[rax*2]
0x18003851b  mov     [rbp+57h+var_64], edx
0x18003851e  mov     edx, 3; UserDataCount
0x180038523  mov     [rbp+57h+var_68], eax
0x180038526  lea     r8, [rbp+57h+UserData]; UserData
0x18003852a  lea     rcx, FVE_AUTODE_HSTI_REPORT_DATA_SIZE; EventDescriptor
0x180038531  call    ?NgscbTryWriteEventLog@@YAXPEBU_EVENT_DESCRIPTOR@@KPEAU_EVENT_DATA_DESCRIPTOR@@@Z; NgscbTryWriteEventLog(_EVENT_DESCRIPTOR const *,ulong,_EVENT_DATA_DESCRIPTOR *)
0x180038536  mov     eax, [rbp+57h+ReturnLength]
0x180038539  cmp     eax, [rbp+57h+var_A8]
0x18003853c  jnb     short loc_180038591
0x18003853e  mov     rcx, cs:WPP_GLOBAL_Control
0x180038545  cmp     rcx, rdi
0x180038548  jz      short loc_18003856B
0x18003854a  test    byte ptr [rcx+1Ch], 2
0x18003854e  jz      short loc_18003856B
0x180038550  mov     rcx, [rcx+10h]
0x180038554  mov     edx, 28h ; '('
0x180038559  mov     r9d, eax
0x18003855c  mov     r8, r15
0x18003855f  call    WPP_SF_d
0x180038564  mov     rcx, cs:WPP_GLOBAL_Control
0x18003856b  mov     r9d, 8007000Dh
0x180038571  mov     r14d, r9d
0x180038574  cmp     rcx, rdi
0x180038577  jz      loc_1800386C0
0x18003857d  test    byte ptr [rcx+1Ch], 40h
0x180038581  jz      loc_1800386C0
0x180038587  mov     edx, 29h ; ')'
0x18003858c  jmp     loc_1800386B4
0x180038591  cmp     eax, 14h
0x180038594  jnb     loc_180038678
0x18003859a  mov     r13, [rbp+57h+SystemInformation]
0x18003859e  add     r13, 4
  ... truncated ...
```
