# CDataPackagePropertySet::get_ContentSourceUserActivityJson(HSTRING__ * *)

- ea: `0x180058360`
- end: `0x18005843f`
- name: `?get_ContentSourceUserActivityJson@CDataPackagePropertySet@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `223`
- prototype: `int(CDataPackagePropertySet *__hidden this, HSTRING *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180058450`

## callees

- `0x18000edc0`
- `0x180048954`
- `0x180054028`
- `0x180058360`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800583e8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800583e8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180058418`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005842a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180058418`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005842a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CDataPackagePropertySet::get_ContentSourceUserActivityJson(
        CDataPackagePropertySet *this,
        HSTRING *a2)
{
  char *v3; // rsi
  int StringValue; // eax
  unsigned int v5; // ebx
  WCHAR *v7; // rcx
  __int64 v8; // rdx
  HRESULT String; // eax
  int v10; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  PCNZWCH sourceString; // [rsp+40h] [rbp+8h] BYREF
  PCNZWCH *p_sourceString; // [rsp+50h] [rbp+18h] BYREF

  v3 = (char *)this - 24;
  StringValue = CDataPackagePropertySet::_GetStringValue(
                  (CDataPackagePropertySet *)((char *)this - 24),
                  L"ContentSourceUserActivity",
                  a2);
  v5 = StringValue;
  if ( StringValue < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x104D,
      (unsigned int)"onecoreuap\\shell\\datatransfer\\lib\\datapackage.cpp",
      (const char *)(unsigned int)StringValue,
      v10);
    return v5;
  }
  if ( !*a2 )
  {
    sourceString = 0;
    p_sourceString = &sourceString;
    CDataPackagePropertySet::_CallDataObjectWithEdpUIPolicyDisabled<_lambda_315dcca2029c58a10a41bf5fb53b336a_>(
      v3,
      &p_sourceString);
    v7 = (WCHAR *)sourceString;
    if ( sourceString )
    {
      v8 = -1;
      do
        ++v8;
      while ( sourceString[v8] );
      String = WindowsCreateString(sourceString, v8, a2);
      v5 = String;
      if ( String < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1059,
          (unsigned int)"onecoreuap\\shell\\datatransfer\\lib\\datapackage.cpp",
          (const char *)(unsigned int)String,
          v10);
        if ( sourceString )
          CoTaskMemFree((LPVOID)sourceString);
        return v5;
      }
      v7 = (WCHAR *)sourceString;
    }
    if ( v7 )
      CoTaskMemFree(v7);
  }
  return 0;
}

```

## disassembly

```asm
0x180058360  mov     [rsp+arg_8], rbx
0x180058365  push    rbp
0x180058366  push    rsi
0x180058367  push    rdi; int
0x180058368  sub     rsp, 20h
0x18005836c  mov     rdi, rdx
0x18005836f  lea     rsi, [rcx-18h]
0x180058373  mov     r8, rdx; HSTRING *
0x180058376  lea     rdx, aContentsourceu; "ContentSourceUserActivity"
0x18005837d  mov     rcx, rsi; this
0x180058380  call    ?_GetStringValue@CDataPackagePropertySet@@AEAAJPEBGPEAPEAUHSTRING__@@@Z; CDataPackagePropertySet::_GetStringValue(ushort const *,HSTRING__ * *)
0x180058385  mov     ebx, eax
0x180058387  xor     ebp, ebp
0x180058389  test    eax, eax
0x18005838b  jns     short loc_1800583AD
0x18005838d  mov     rcx, [rsp+38h]; this
0x180058392  mov     r9d, eax; char *
0x180058395  lea     r8, aOnecoreuapShel; "onecoreuap\\shell\\datatransfer\\lib\\d"...
0x18005839c  mov     edx, 104Dh; void *
0x1800583a1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800583a6  mov     eax, ebx
0x1800583a8  jmp     loc_180058432
0x1800583ad  cmp     [rdi], rbp
0x1800583b0  jnz     short loc_180058430
0x1800583b2  mov     [rsp+38h+sourceString], rbp
0x1800583b7  lea     rax, [rsp+38h+sourceString]
0x1800583bc  mov     [rsp+38h+arg_10], rax
0x1800583c1  lea     rdx, [rsp+38h+arg_10]
0x1800583c6  mov     rcx, rsi
0x1800583c9  call    ??$_CallDataObjectWithEdpUIPolicyDisabled@V_lambda_315dcca2029c58a10a41bf5fb53b336a_@@@CDataPackagePropertySet@@AEAAJ$$QEAV_lambda_315dcca2029c58a10a41bf5fb53b336a_@@@Z; CDataPackagePropertySet::_CallDataObjectWithEdpUIPolicyDisabled<_lambda_315dcca2029c58a10a41bf5fb53b336a_>(_lambda_315dcca2029c58a10a41bf5fb53b336a_ &&)
0x1800583ce  mov     rcx, [rsp+38h+sourceString]; sourceString
0x1800583d3  test    rcx, rcx
0x1800583d6  jz      short loc_180058425
0x1800583d8  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800583dc  inc     rdx; length
0x1800583df  cmp     [rcx+rdx*2], bp
0x1800583e3  jnz     short loc_1800583DC
0x1800583e5  mov     r8, rdi; string
0x1800583e8  call    cs:__imp_WindowsCreateString
0x1800583ee  mov     ebx, eax
0x1800583f0  test    eax, eax
0x1800583f2  jns     short loc_180058420
0x1800583f4  mov     rcx, [rsp+38h]; this
0x1800583f9  mov     r9d, eax; char *
0x1800583fc  lea     r8, aOnecoreuapShel; "onecoreuap\\shell\\datatransfer\\lib\\d"...
0x180058403  mov     edx, 1059h; void *
0x180058408  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005840d  nop
0x18005840e  mov     rcx, [rsp+38h+sourceString]; pv
0x180058413  test    rcx, rcx
0x180058416  jz      short loc_1800583A6
0x180058418  call    cs:__imp_CoTaskMemFree
0x18005841e  jmp     short loc_1800583A6
0x180058420  mov     rcx, [rsp+38h+sourceString]; pv
0x180058425  test    rcx, rcx
0x180058428  jz      short loc_180058430
0x18005842a  call    cs:__imp_CoTaskMemFree
0x180058430  xor     eax, eax
0x180058432  mov     rbx, [rsp+38h+arg_8]
0x180058437  add     rsp, 20h
0x18005843b  pop     rdi
0x18005843c  pop     rsi
0x18005843d  pop     rbp
0x18005843e  retn
```
