# EtwpInitializeAutoLoggers

- ea: `0x1407df8e0`
- end: `0x1407dfbb9`
- name: `EtwpInitializeAutoLoggers`
- size: `729`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1407d9514`

## callees

- `0x1403e3960`
- `0x140462850`
- `0x1406dc8c0`
- `0x1406f7380`
- `0x1407df5d8`
- `0x1407df8ac`
- `0x1407df8e0`
- `0x140879b80`
- `0x140adfc3c`
- `0x140bb1410`
- `0x140bb19f0`
- `0x140c864b8`

## string_xrefs

- `0x1407dfabb`: `ETWAutoLoggerPath`
- `0x1407dfb0b`: `ETWGlobalLoggerPath`
- `0x1407df909`: `\Registry\Machine\System\CurrentControlSet\Control\WMI\AutoLogger`
- `0x1407df982`: `\Registry\Machine\System\CurrentControlSet\Control\WMI\GlobalLogger`

## pseudocode

```c
__int64 __fastcall EtwpInitializeAutoLoggers(__int64 a1)
{
  _QWORD *v2; // rbx
  _QWORD *i; // rdi
  _WORD *v4; // rdx
  __int64 v5; // r8
  void *Pool2; // rbx
  void *v7; // rdi
  BOOLEAN NewElement[4]; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v10; // [rsp+44h] [rbp-BCh] BYREF
  RTL_AVL_TABLE Table; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR SourceString[16]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR Path[72]; // [rsp+E0h] [rbp-20h] BYREF
  __int128 v14; // [rsp+170h] [rbp+70h]
  __int128 v15; // [rsp+180h] [rbp+80h]
  __int128 v16; // [rsp+190h] [rbp+90h]
  __int128 v17; // [rsp+1A0h] [rbp+A0h]
  __int128 v18; // [rsp+1B0h] [rbp+B0h]
  __int128 v19; // [rsp+1C0h] [rbp+C0h]
  __int128 v20; // [rsp+1D0h] [rbp+D0h]
  __int128 v21; // [rsp+1E0h] [rbp+E0h]
  __int64 v22; // [rsp+1F0h] [rbp+F0h]

  wcscpy(Path, L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\WMI\\AutoLogger");
  v22 = *(_QWORD *)L"ger";
  v14 = *(_OWORD *)L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\WMI\\GlobalLogger";
  v15 = *(_OWORD *)L"y\\Machine\\System\\CurrentControlSet\\Control\\WMI\\GlobalLogger";
  v16 = *(_OWORD *)L"e\\System\\CurrentControlSet\\Control\\WMI\\GlobalLogger";
  v17 = *(_OWORD *)L"\\CurrentControlSet\\Control\\WMI\\GlobalLogger";
  v18 = *(_OWORD *)L"ControlSet\\Control\\WMI\\GlobalLogger";
  v19 = *(_OWORD *)L"et\\Control\\WMI\\GlobalLogger";
  v20 = *(_OWORD *)L"ol\\WMI\\GlobalLogger";
  v21 = *(_OWORD *)L"lobalLogger";
  wcscpy(SourceString, L"GllLogger");
  memset_0(&Table, 0, sizeof(Table));
  RtlInitializeGenericTableAvl(&Table, EtwpAvlCompareKeyNames, EtwpAllocateKeyNameEntry, EtwpFreeKeyNameEntry, 0);
  if ( a1 )
  {
    v2 = (_QWORD *)(a1 + 8);
    if ( (_QWORD *)*v2 != v2 )
    {
      EtwpEnableBootLoggerRegistryProviders(Path, a1);
      for ( i = (_QWORD *)*v2; i != v2; i = (_QWORD *)*i )
      {
        v4 = (_WORD *)i[2];
        v5 = -1;
        do
          ++v5;
        while ( v4[v5] );
        RtlInsertElementGenericTableAvl(&Table, v4, 2 * v5 + 2, NewElement);
      }
    }
  }
  Pool2 = (void *)ExAllocatePool2(256, 520, 1953985605);
  if ( Pool2 )
  {
    if ( (unsigned int)RtlGetPersistedStateLocation(L"ETWAutoLoggerPath", Pool2, 520, (__int64)&v10) )
    {
      ExFreePoolWithTag(Pool2, 0x74777445u);
      Pool2 = 0;
    }
    v7 = (void *)ExAllocatePool2(256, 520, 1953985605);
    if ( v7 )
    {
      if ( (unsigned int)RtlGetPersistedStateLocation(L"ETWGlobalLoggerPath", v7, 520, (__int64)&v10) )
      {
        ExFreePoolWithTag(v7, 0x74777445u);
        v7 = 0;
      }
      EtwStartAutoLogger(SourceString);
      EtwpEnumerateAutologgerPath(Path);
      if ( !Pool2 )
        goto LABEL_18;
      EtwpEnumerateAutologgerPath((PCWSTR)Pool2);
    }
    else if ( !Pool2 )
    {
      return EtwpFreeKeyNameList(&Table);
    }
    ExFreePoolWithTag(Pool2, 0x74777445u);
LABEL_18:
    if ( v7 )
      ExFreePoolWithTag(v7, 0x74777445u);
  }
  return EtwpFreeKeyNameList(&Table);
}

```

## disassembly

```asm
0x1407df8e0  push    rbp
0x1407df8e2  push    rbx
0x1407df8e3  push    rsi
0x1407df8e4  push    rdi
0x1407df8e5  push    r14
0x1407df8e7  push    r15
0x1407df8e9  lea     rbp, [rsp-118h]
0x1407df8f1  sub     rsp, 218h
0x1407df8f8  mov     rax, cs:__security_cookie
0x1407df8ff  xor     rax, rsp
0x1407df902  mov     [rbp+140h+var_40], rax
0x1407df909  movaps  xmm0, xmmword ptr cs:aRegistryMachin_92; "\\Registry\\Machine\\System\\CurrentCon"...
0x1407df910  xor     edx, edx; Val
0x1407df912  movaps  xmm1, xmmword ptr cs:aRegistryMachin_92+10h; "y\\Machine\\System\\CurrentControlSet\\"...
0x1407df919  mov     rdi, rcx
0x1407df91c  mov     eax, dword ptr cs:aRegistryMachin_92+80h; "r"
0x1407df922  lea     rcx, [rsp+240h+Table]; void *
0x1407df927  movups  xmmword ptr [rbp+140h+Path], xmm0
0x1407df92b  lea     r8d, [rdx+68h]; Size
0x1407df92f  mov     [rbp+140h+var_E0], eax
0x1407df932  movaps  xmm0, xmmword ptr cs:aRegistryMachin_92+20h; "e\\System\\CurrentControlSet\\Control\\"...
0x1407df939  mov     rax, qword ptr cs:aRegistryMachin_63+80h; "ger"
0x1407df940  movups  [rbp+140h+var_150], xmm1
0x1407df944  mov     [rbp+140h+var_50], rax
0x1407df94b  movaps  xmm1, xmmword ptr cs:aRegistryMachin_92+30h; "\\CurrentControlSet\\Control\\WMI\\Auto"...
0x1407df952  movups  [rbp+140h+var_140], xmm0
0x1407df956  movaps  xmm0, xmmword ptr cs:aRegistryMachin_92+40h; "ControlSet\\Control\\WMI\\AutoLogger"
0x1407df95d  movups  [rbp+140h+var_130], xmm1
0x1407df961  movaps  xmm1, xmmword ptr cs:aRegistryMachin_92+50h; "et\\Control\\WMI\\AutoLogger"
0x1407df968  movups  [rbp+140h+var_120], xmm0
0x1407df96c  movaps  xmm0, xmmword ptr cs:aRegistryMachin_92+60h; "ol\\WMI\\AutoLogger"
0x1407df973  movups  [rbp+140h+var_110], xmm1
0x1407df977  movaps  xmm1, xmmword ptr cs:aRegistryMachin_92+70h; "utoLogger"
0x1407df97e  movups  [rbp+140h+var_100], xmm0
0x1407df982  movaps  xmm0, xmmword ptr cs:aRegistryMachin_63; "\\Registry\\Machine\\System\\CurrentCon"...
0x1407df989  movups  [rbp+140h+var_F0], xmm1
0x1407df98d  movaps  xmm1, xmmword ptr cs:aRegistryMachin_63+10h; "y\\Machine\\System\\CurrentControlSet\\"...
0x1407df994  movups  [rbp+140h+var_D0], xmm0
0x1407df998  movaps  xmm0, xmmword ptr cs:aRegistryMachin_63+20h; "e\\System\\CurrentControlSet\\Control\\"...
0x1407df99f  movups  [rbp+140h+var_C0], xmm1
0x1407df9a6  movaps  xmm1, xmmword ptr cs:aRegistryMachin_63+30h; "\\CurrentControlSet\\Control\\WMI\\Glob"...
0x1407df9ad  movups  [rbp+140h+var_B0], xmm0
0x1407df9b4  movaps  xmm0, xmmword ptr cs:aRegistryMachin_63+40h; "ControlSet\\Control\\WMI\\GlobalLogger"
0x1407df9bb  movups  [rbp+140h+var_A0], xmm1
0x1407df9c2  movaps  xmm1, xmmword ptr cs:aRegistryMachin_63+50h; "et\\Control\\WMI\\GlobalLogger"
0x1407df9c9  movups  [rbp+140h+var_90], xmm0
0x1407df9d0  movaps  xmm0, xmmword ptr cs:aRegistryMachin_63+60h; "ol\\WMI\\GlobalLogger"
0x1407df9d7  movups  [rbp+140h+var_80], xmm1
0x1407df9de  movaps  xmm1, xmmword ptr cs:aRegistryMachin_63+70h; "lobalLogger"
0x1407df9e5  movups  [rbp+140h+var_70], xmm0
0x1407df9ec  movups  xmm0, xmmword ptr cs:aGloballogger; "GlobalLogger"
0x1407df9f3  movups  [rbp+140h+var_60], xmm1
0x1407df9fa  movups  xmm1, xmmword ptr cs:aGloballogger+0Ah; "lLogger"
0x1407dfa01  movups  xmmword ptr [rbp+140h+SourceString], xmm0
0x1407dfa05  movups  xmmword ptr [rbp+140h+SourceString+0Ah], xmm1
0x1407dfa09  call    memset_0
0x1407dfa0e  xor     esi, esi
0x1407dfa10  lea     r9, EtwpFreeKeyNameEntry; FreeRoutine
0x1407dfa17  lea     r8, EtwpAllocateKeyNameEntry; AllocateRoutine
0x1407dfa1e  mov     [rsp+240h+TableContext], rsi; TableContext
0x1407dfa23  lea     rdx, EtwpAvlCompareKeyNames; CompareRoutine
0x1407dfa2a  lea     rcx, [rsp+240h+Table]; Table
0x1407dfa2f  call    RtlInitializeGenericTableAvl
0x1407dfa34  test    rdi, rdi
0x1407dfa37  jz      short loc_1407DFA84
0x1407dfa39  lea     rbx, [rdi+8]
0x1407dfa3d  cmp     [rbx], rbx
0x1407dfa40  jz      short loc_1407DFA84
0x1407dfa42  mov     rdx, rdi
0x1407dfa45  lea     rcx, [rbp+140h+Path]
0x1407dfa49  call    EtwpEnableBootLoggerRegistryProviders
0x1407dfa4e  mov     rdi, [rbx]
0x1407dfa51  jmp     short loc_1407DFA7F
0x1407dfa53  mov     rdx, [rdi+10h]; Buffer
0x1407dfa57  or      r8, 0FFFFFFFFFFFFFFFFh
0x1407dfa5b  inc     r8
0x1407dfa5e  cmp     [rdx+r8*2], si
0x1407dfa63  jnz     short loc_1407DFA5B
0x1407dfa65  lea     r8d, ds:2[r8*2]; BufferSize
0x1407dfa6d  lea     r9, [rsp+240h+NewElement]; NewElement
0x1407dfa72  lea     rcx, [rsp+240h+Table]; Table
0x1407dfa77  call    RtlInsertElementGenericTableAvl
0x1407dfa7c  mov     rdi, [rdi]
0x1407dfa7f  cmp     rdi, rbx
0x1407dfa82  jnz     short loc_1407DFA53
0x1407dfa84  mov     r14d, 74777445h
0x1407dfa8a  mov     r15d, 208h
0x1407dfa90  mov     edi, 100h
0x1407dfa95  mov     r8d, r14d
0x1407dfa98  mov     edx, r15d
0x1407dfa9b  mov     ecx, edi
0x1407dfa9d  call    ExAllocatePool2
0x1407dfaa2  mov     rbx, rax
0x1407dfaa5  test    rax, rax
0x1407dfaa8  jz      loc_1407DFB8F
0x1407dfaae  lea     rax, [rsp+240h+var_1FC]
0x1407dfab3  xor     r9d, r9d
0x1407dfab6  mov     [rsp+240h+var_210], rax; __int64
0x1407dfabb  lea     rcx, aEtwautologgerp; "ETWAutoLoggerPath"
0x1407dfac2  mov     [rsp+240h+var_218], r15d; int
0x1407dfac7  xor     r8d, r8d
0x1407dfaca  xor     edx, edx
0x1407dfacc  mov     [rsp+240h+TableContext], rbx; void *
0x1407dfad1  call    RtlGetPersistedStateLocation
0x1407dfad6  test    eax, eax
0x1407dfad8  jz      short loc_1407DFAE8
0x1407dfada  mov     edx, r14d; Tag
0x1407dfadd  mov     rcx, rbx; P
0x1407dfae0  call    ExFreePoolWithTag
0x1407dfae5  mov     rbx, rsi
0x1407dfae8  mov     r8d, r14d
0x1407dfaeb  mov     rdx, r15
0x1407dfaee  mov     rcx, rdi
0x1407dfaf1  call    ExAllocatePool2
0x1407dfaf6  mov     rdi, rax
0x1407dfaf9  test    rax, rax
0x1407dfafc  jz      short loc_1407DFB6F
0x1407dfafe  lea     rax, [rsp+240h+var_1FC]
0x1407dfb03  xor     r9d, r9d
0x1407dfb06  mov     [rsp+240h+var_210], rax; __int64
0x1407dfb0b  lea     rcx, aEtwgloballogge; "ETWGlobalLoggerPath"
0x1407dfb12  mov     [rsp+240h+var_218], r15d; int
0x1407dfb17  xor     r8d, r8d
0x1407dfb1a  xor     edx, edx
0x1407dfb1c  mov     [rsp+240h+TableContext], rdi; void *
0x1407dfb21  call    RtlGetPersistedStateLocation
0x1407dfb26  test    eax, eax
0x1407dfb28  jz      short loc_1407DFB38
0x1407dfb2a  mov     edx, r14d; Tag
0x1407dfb2d  mov     rcx, rdi; P
0x1407dfb30  call    ExFreePoolWithTag
0x1407dfb35  mov     rdi, rsi
0x1407dfb38  mov     r8, rdi
0x1407dfb3b  lea     rdx, [rbp+140h+var_D0]
0x1407dfb3f  lea     rcx, [rbp+140h+SourceString]; SourceString
0x1407dfb43  call    EtwStartAutoLogger
0x1407dfb48  lea     r8, [rsp+240h+Table]
0x1407dfb4d  mov     rdx, rbx
0x1407dfb50  lea     rcx, [rbp+140h+Path]; Path
0x1407dfb54  call    EtwpEnumerateAutologgerPath
0x1407dfb59  test    rbx, rbx
0x1407dfb5c  jz      short loc_1407DFB7F
0x1407dfb5e  lea     r8, [rsp+240h+Table]
0x1407dfb63  xor     edx, edx
0x1407dfb65  mov     rcx, rbx; Path
0x1407dfb68  call    EtwpEnumerateAutologgerPath
0x1407dfb6d  jmp     short loc_1407DFB74
0x1407dfb6f  test    rbx, rbx
0x1407dfb72  jz      short loc_1407DFB8F
0x1407dfb74  mov     edx, r14d; Tag
0x1407dfb77  mov     rcx, rbx; P
0x1407dfb7a  call    ExFreePoolWithTag
0x1407dfb7f  test    rdi, rdi
0x1407dfb82  jz      short loc_1407DFB8F
0x1407dfb84  mov     edx, r14d; Tag
0x1407dfb87  mov     rcx, rdi; P
0x1407dfb8a  call    ExFreePoolWithTag
0x1407dfb8f  lea     rcx, [rsp+240h+Table]; Table
0x1407dfb94  call    EtwpFreeKeyNameList
0x1407dfb99  mov     rcx, [rbp+140h+var_40]
0x1407dfba0  xor     rcx, rsp; StackCookie
0x1407dfba3  call    __security_check_cookie
0x1407dfba8  add     rsp, 218h
0x1407dfbaf  pop     r15
0x1407dfbb1  pop     r14
0x1407dfbb3  pop     rdi
0x1407dfbb4  pop     rsi
0x1407dfbb5  pop     rbx
0x1407dfbb6  pop     rbp
0x1407dfbb7  retn
```
