# EnterpriseFeatureControl::GetFeatureStatusCache(ulong,bool *,bool *)

- ea: `0x1800325c8`
- end: `0x1800327cb`
- name: `?GetFeatureStatusCache@EnterpriseFeatureControl@@CAJKPEA_N0@Z`
- size: `515`
- prototype: `__int64 __fastcall(unsigned int, bool *, bool *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800359e4`

## callees

- `0x1800183d4`
- `0x1800183f4`
- `0x1800298cc`
- `0x1800325c8`
- `0x180032834`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003265f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800326ba`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003273f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180032796`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800327af`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003265f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800326ba`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003273f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180032796`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800327af`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180032651`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800326ac`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180032731`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180032788`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800327a1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180032651`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800326ac`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180032731`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180032788`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800327a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032685`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032685`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18003276c`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18003276c`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x180032679`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x180032711`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x180032679`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x180032711`

## pseudocode

```c
__int64 __fastcall EnterpriseFeatureControl::GetFeatureStatusCache(unsigned int a1, bool *a2, bool *a3)
{
  __int64 v5; // rdx
  int ProcessEnvName; // eax
  unsigned int v8; // edi
  void *v9; // rbx
  HANDLE ProcessHeap; // rax
  DWORD EnvironmentVariableW; // eax
  __int64 v12; // rdx
  __int64 v13; // rsi
  signed int LastError; // eax
  unsigned int v15; // esi
  HANDLE v16; // rax
  __int64 v17; // rdx
  void *v18; // rdi
  const char *v19; // r9
  HANDLE v20; // rax
  bool v21; // al
  HANDLE v22; // rax
  HANDLE v23; // rax
  int lpString2; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  LPVOID lpMem; // [rsp+58h] [rbp+10h] BYREF

  if ( !a2 )
  {
    v5 = 56;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"onecore\\internal\\enduser\\inc\\EnterpriseFeatureControl.h",
      (const char *)0x80004003LL,
      lpString2);
    return 2147500035LL;
  }
  if ( !a3 )
  {
    v5 = 57;
    goto LABEL_3;
  }
  lpMem = 0;
  ProcessEnvName = EnterpriseFeatureControl::GetProcessEnvName(a1, (unsigned __int16 **)&lpMem);
  v8 = ProcessEnvName;
  if ( ProcessEnvName < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3C,
      (unsigned int)"onecore\\internal\\enduser\\inc\\EnterpriseFeatureControl.h",
      (const char *)(unsigned int)ProcessEnvName,
      lpString2);
    v9 = lpMem;
LABEL_8:
    if ( v9 )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v9);
    }
    return v8;
  }
  v9 = lpMem;
  EnvironmentVariableW = GetEnvironmentVariableW((LPCWSTR)lpMem, 0, 0);
  v13 = EnvironmentVariableW;
  if ( !EnvironmentVariableW )
  {
    LastError = GetLastError();
    v8 = LastError;
    if ( LastError > 0 )
      v8 = (unsigned __int16)LastError | 0x80070000;
    if ( (v8 & 0x80000000) != 0 )
    {
      v15 = -2147024693;
      if ( v8 == -2147024693 )
      {
LABEL_16:
        if ( v9 )
        {
          v16 = GetProcessHeap();
          HeapFree(v16, 0, v9);
        }
        return v15;
      }
      v17 = 65;
LABEL_20:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v17,
        (unsigned int)"onecore\\internal\\enduser\\inc\\EnterpriseFeatureControl.h",
        (const char *)v8,
        lpString2);
      goto LABEL_8;
    }
  }
  wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
    &lpMem,
    v12,
    v13);
  v18 = lpMem;
  if ( !lpMem )
  {
    v8 = -2147024882;
    v17 = 69;
    goto LABEL_20;
  }
  if ( !GetEnvironmentVariableW((LPCWSTR)v9, (LPWSTR)lpMem, v13) )
  {
    v15 = wil::details::in1diag3::Return_GetLastError(
            retaddr,
            (void *)0x48,
            (unsigned int)"onecore\\internal\\enduser\\inc\\EnterpriseFeatureControl.h",
            v19);
    v20 = GetProcessHeap();
    HeapFree(v20, 0, v18);
    goto LABEL_16;
  }
  if ( v18 )
    v21 = CompareStringW(0x7Fu, 0, (PCNZWCH)v18, -1, L"1", -1) == 2;
  else
    v21 = 0;
  *a3 = v21;
  *a2 = 1;
  if ( v18 )
  {
    v22 = GetProcessHeap();
    HeapFree(v22, 0, v18);
  }
  if ( v9 )
  {
    v23 = GetProcessHeap();
    HeapFree(v23, 0, v9);
  }
  return 0;
}

```

## disassembly

```asm
0x1800325c8  mov     [rsp+arg_0], rbx
0x1800325cd  mov     [rsp+arg_10], rsi
0x1800325d2  push    rdi
0x1800325d3  push    r14
0x1800325d5  push    r15
0x1800325d7  sub     rsp, 30h
0x1800325db  mov     r14, r8
0x1800325de  mov     r15, rdx
0x1800325e1  test    rdx, rdx
0x1800325e4  jnz     short loc_18003260A
0x1800325e6  lea     edx, [r15+38h]; void *
0x1800325ea  mov     rcx, [rsp+48h]; this
0x1800325ef  lea     r8, aOnecoreInterna_5; "onecore\\internal\\enduser\\inc\\Enterp"...
0x1800325f6  mov     ebx, 80004003h
0x1800325fb  mov     r9d, ebx; char *
0x1800325fe  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180032603  mov     eax, ebx
0x180032605  jmp     loc_1800327B7
0x18003260a  test    r14, r14
0x18003260d  jnz     short loc_180032615
0x18003260f  lea     edx, [r14+39h]
0x180032613  jmp     short loc_1800325EA
0x180032615  lea     rdx, [rsp+48h+lpMem]; unsigned __int16 **
0x18003261a  mov     [rsp+48h+lpMem], 0
0x180032623  call    ?GetProcessEnvName@EnterpriseFeatureControl@@CAJKPEAPEAG@Z; EnterpriseFeatureControl::GetProcessEnvName(ulong,ushort * *)
0x180032628  mov     edi, eax
0x18003262a  test    eax, eax
0x18003262c  jns     short loc_18003266C
0x18003262e  mov     rcx, [rsp+48h]; this
0x180032633  lea     r8, aOnecoreInterna_5; "onecore\\internal\\enduser\\inc\\Enterp"...
0x18003263a  mov     r9d, eax; char *
0x18003263d  mov     edx, 3Ch ; '<'; void *
0x180032642  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180032647  mov     rbx, [rsp+48h+lpMem]
0x18003264c  test    rbx, rbx
0x18003264f  jz      short loc_180032665
0x180032651  call    cs:__imp_GetProcessHeap
0x180032657  mov     r8, rbx; lpMem
0x18003265a  xor     edx, edx; dwFlags
0x18003265c  mov     rcx, rax; hHeap
0x18003265f  call    cs:__imp_HeapFree
0x180032665  mov     eax, edi
0x180032667  jmp     loc_1800327B7
0x18003266c  mov     rbx, [rsp+48h+lpMem]
0x180032671  xor     r8d, r8d; nSize
0x180032674  mov     rcx, rbx; lpName
0x180032677  xor     edx, edx; lpBuffer
0x180032679  call    cs:__imp_GetEnvironmentVariableW
0x18003267f  mov     esi, eax
0x180032681  test    eax, eax
0x180032683  jnz     short loc_1800326E5
0x180032685  call    cs:__imp_GetLastError
0x18003268b  mov     edi, eax
0x18003268d  test    eax, eax
0x18003268f  jle     short loc_18003269A
0x180032691  movzx   edi, ax
0x180032694  or      edi, 80070000h
0x18003269a  test    edi, edi
0x18003269c  jns     short loc_1800326E5
0x18003269e  mov     esi, 800700CBh
0x1800326a3  cmp     edi, esi
0x1800326a5  jnz     short loc_1800326C7
0x1800326a7  test    rbx, rbx
0x1800326aa  jz      short loc_1800326C0
0x1800326ac  call    cs:__imp_GetProcessHeap
0x1800326b2  mov     r8, rbx; lpMem
0x1800326b5  xor     edx, edx; dwFlags
0x1800326b7  mov     rcx, rax; hHeap
0x1800326ba  call    cs:__imp_HeapFree
0x1800326c0  mov     eax, esi
0x1800326c2  jmp     loc_1800327B7
0x1800326c7  mov     edx, 41h ; 'A'; void *
0x1800326cc  mov     rcx, [rsp+48h]; this
0x1800326d1  lea     r8, aOnecoreInterna_5; "onecore\\internal\\enduser\\inc\\Enterp"...
0x1800326d8  mov     r9d, edi; char *
0x1800326db  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800326e0  jmp     loc_18003264C
0x1800326e5  mov     r8, rsi
0x1800326e8  lea     rcx, [rsp+48h+lpMem]
0x1800326ed  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x1800326f2  mov     rdi, [rsp+48h+lpMem]
0x1800326f7  test    rdi, rdi
0x1800326fa  jnz     short loc_180032708
0x1800326fc  mov     edi, 8007000Eh
0x180032701  mov     edx, 45h ; 'E'
0x180032706  jmp     short loc_1800326CC
0x180032708  mov     r8d, esi; nSize
0x18003270b  mov     rdx, rdi; lpBuffer
0x18003270e  mov     rcx, rbx; lpName
0x180032711  call    cs:__imp_GetEnvironmentVariableW
0x180032717  test    eax, eax
0x180032719  jnz     short loc_18003274A
0x18003271b  mov     rcx, [rsp+48h]; this
0x180032720  lea     r8, aOnecoreInterna_5; "onecore\\internal\\enduser\\inc\\Enterp"...
0x180032727  lea     edx, [rax+48h]; void *
0x18003272a  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18003272f  mov     esi, eax
0x180032731  call    cs:__imp_GetProcessHeap
0x180032737  mov     r8, rdi; lpMem
0x18003273a  xor     edx, edx; dwFlags
0x18003273c  mov     rcx, rax; hHeap
0x18003273f  call    cs:__imp_HeapFree
0x180032745  jmp     loc_1800326A7
0x18003274a  test    rdi, rdi
0x18003274d  jz      short loc_18003277A
0x18003274f  xor     edx, edx; dwCmpFlags
0x180032751  lea     rax, String2; "1"
0x180032758  or      r9d, 0FFFFFFFFh; cchCount1
0x18003275c  mov     r8, rdi; lpString1
0x18003275f  mov     [rsp+48h+cchCount2], r9d; cchCount2
0x180032764  mov     [rsp+48h+lpString2], rax; lpString2
0x180032769  lea     ecx, [rdx+7Fh]; Locale
0x18003276c  call    cs:__imp_CompareStringW
0x180032772  cmp     eax, 2
0x180032775  setz    al
0x180032778  jmp     short loc_18003277C
0x18003277a  xor     al, al
0x18003277c  mov     [r14], al
0x18003277f  mov     byte ptr [r15], 1
0x180032783  test    rdi, rdi
0x180032786  jz      short loc_18003279C
0x180032788  call    cs:__imp_GetProcessHeap
0x18003278e  mov     r8, rdi; lpMem
0x180032791  xor     edx, edx; dwFlags
0x180032793  mov     rcx, rax; hHeap
0x180032796  call    cs:__imp_HeapFree
0x18003279c  test    rbx, rbx
0x18003279f  jz      short loc_1800327B5
0x1800327a1  call    cs:__imp_GetProcessHeap
0x1800327a7  mov     r8, rbx; lpMem
0x1800327aa  xor     edx, edx; dwFlags
0x1800327ac  mov     rcx, rax; hHeap
0x1800327af  call    cs:__imp_HeapFree
0x1800327b5  xor     eax, eax
0x1800327b7  mov     rbx, [rsp+48h+arg_0]
0x1800327bc  mov     rsi, [rsp+48h+arg_10]
0x1800327c1  add     rsp, 30h
0x1800327c5  pop     r15
0x1800327c7  pop     r14
0x1800327c9  pop     rdi
0x1800327ca  retn
```
