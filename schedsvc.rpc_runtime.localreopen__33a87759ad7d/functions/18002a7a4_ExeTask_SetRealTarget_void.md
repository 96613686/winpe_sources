# ExeTask::SetRealTarget(void)

- ea: `0x18002a7a4`
- end: `0x18002a9d4`
- name: `?SetRealTarget@ExeTask@@IEAAJXZ`
- size: `560`
- prototype: `__int64 __fastcall(ExeTask *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18002a4ac`

## callees

- `0x18002a7a4`
- `0x1800339c0`
- `0x18004ae94`
- `0x1800555a0`
- `0x18005f3fc`
- `0x18005f4a4`
- `0x18007e6d0`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18002a949`
- `msvcrt!_wcsicmp` at `0x18002a949`
- `msvcrt!wcsrchr` at `0x18002a7ee`
- `msvcrt!wcsrchr` at `0x18002a913`
- `msvcrt!wcsrchr` at `0x18002a7ee`
- `msvcrt!wcsrchr` at `0x18002a913`
- `api-ms-win-core-processenvironment-l1-1-0!SearchPathW` at `0x18002a8a6`
- `api-ms-win-core-processenvironment-l1-1-0!SearchPathW` at `0x18002a8e0`
- `api-ms-win-core-processenvironment-l1-1-0!SearchPathW` at `0x18002a8a6`
- `api-ms-win-core-processenvironment-l1-1-0!SearchPathW` at `0x18002a8e0`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall ExeTask::SetRealTarget(ExeTask *this)
{
  const wchar_t ***v1; // rbx
  const wchar_t **v2; // rax
  const wchar_t *v4; // rcx
  wchar_t *v5; // rax
  __int64 v6; // rsi
  __int64 v7; // rcx
  __int64 result; // rax
  unsigned int i; // ebp
  const WCHAR *v10; // rdx
  const WCHAR **v11; // rax
  const WCHAR *v12; // rcx
  const WCHAR *v13; // rdx
  const wchar_t *v14; // rcx
  wchar_t *v15; // rax
  LPWSTR v16; // rbx
  LPWSTR FilePart[2]; // [rsp+30h] [rbp-258h] BYREF
  WCHAR Buffer[264]; // [rsp+40h] [rbp-248h] BYREF

  v1 = (const wchar_t ***)((char *)this + 48);
  v2 = (const wchar_t **)*((_QWORD *)this + 6);
  if ( v2 )
    v4 = *v2;
  else
    v4 = 0;
  v5 = wcsrchr(v4, 0x2Eu);
  v6 = -1;
  *((_DWORD *)this + 10) = 0;
  if ( v5 )
  {
    v7 = -1;
    do
      ++v7;
    while ( v5[v7] );
    if ( v7 == 1 )
      return 1;
  }
  else
  {
    FilePart[0] = 0;
    for ( i = 0; i < ExtsFound; ++i )
    {
      if ( *v1 )
        v10 = **v1;
      else
        v10 = 0;
      v11 = (const WCHAR **)*((_QWORD *)this + 8);
      if ( v11 )
        v12 = *v11;
      else
        v12 = 0;
      if ( !SearchPathW(v12, v10, (LPCWSTR)(&PathExts)[i], 0x105u, Buffer, FilePart) )
      {
        v13 = *v1 ? **v1 : 0LL;
        if ( !SearchPathW(0, v13, (LPCWSTR)(&PathExts)[i], 0x105u, Buffer, FilePart) )
          continue;
      }
      _bstr_t::operator=(v1, Buffer);
      break;
    }
  }
  if ( *v1 )
    v14 = **v1;
  else
    v14 = 0;
  v15 = wcsrchr(v14, 0x2Eu);
  FilePart[0] = v15;
  v16 = v15;
  if ( !v15 )
    return 1;
  do
    ++v6;
  while ( v15[v6] );
  if ( v6 == 1 )
    return 1;
  if ( _wcsicmp(v15 + 1, L"LNK") )
    goto LABEL_35;
  result = ExeTask::ResolveLink(this, FilePart);
  if ( (int)result >= 0 )
  {
    if ( (_DWORD)result == 1 )
      return 0;
    v16 = FilePart[0];
LABEL_35:
    if ( !IsOnList(v16 + 1, (const unsigned __int16 **)&off_1800BC010, 2) )
    {
      if ( IsOnList(v16 + 1, (const unsigned __int16 **)&off_1800BC340, 3) )
      {
        if ( (int)ExeTask::SetBatchLaunchCommand(this) >= 0 )
          *((_DWORD *)this + 10) = 1;
      }
      else if ( (int)ExeTask::ResolveDocRunAssociation(this, v16) >= 0 )
      {
        *((_DWORD *)this + 10) = 2;
      }
    }
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x18002a7a4  mov     [rsp+arg_8], rbx
0x18002a7a9  mov     [rsp+arg_10], rbp
0x18002a7ae  push    rsi
0x18002a7af  push    rdi
0x18002a7b0  push    r12
0x18002a7b2  push    r14
0x18002a7b4  push    r15
0x18002a7b6  sub     rsp, 260h
0x18002a7bd  mov     rax, cs:__security_cookie
0x18002a7c4  xor     rax, rsp
0x18002a7c7  mov     [rsp+288h+var_38], rax
0x18002a7cf  lea     rbx, [rcx+30h]
0x18002a7d3  xor     r15d, r15d
0x18002a7d6  mov     rax, [rbx]
0x18002a7d9  mov     rdi, rcx
0x18002a7dc  test    rax, rax
0x18002a7df  jz      short loc_18002A7E6
0x18002a7e1  mov     rcx, [rax]
0x18002a7e4  jmp     short loc_18002A7E9
0x18002a7e6  mov     rcx, r15; Str
0x18002a7e9  mov     edx, 2Eh ; '.'; Ch
0x18002a7ee  call    cs:__imp_wcsrchr
0x18002a7f4  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18002a7f8  mov     [rdi+28h], r15d
0x18002a7fc  test    rax, rax
0x18002a7ff  jz      short loc_18002A849
0x18002a801  mov     rcx, rsi
0x18002a804  inc     rcx
0x18002a807  cmp     [rax+rcx*2], r15w
0x18002a80c  jnz     short loc_18002A804
0x18002a80e  cmp     rcx, 1
0x18002a812  jnz     loc_18002A8FE
0x18002a818  mov     eax, 1
0x18002a81d  mov     rcx, [rsp+288h+var_38]
0x18002a825  xor     rcx, rsp; StackCookie
0x18002a828  call    __security_check_cookie
0x18002a82d  lea     r11, [rsp+288h+var_28]
0x18002a835  mov     rbx, [r11+38h]
0x18002a839  mov     rbp, [r11+40h]
0x18002a83d  mov     rsp, r11
0x18002a840  pop     r15
0x18002a842  pop     r14
0x18002a844  pop     r12
0x18002a846  pop     rdi
0x18002a847  pop     rsi
0x18002a848  retn
0x18002a849  mov     [rsp+288h+FilePart], r15
0x18002a84e  mov     ebp, r15d
0x18002a851  cmp     ebp, cs:?ExtsFound@@3KA; ulong ExtsFound
0x18002a857  jnb     loc_18002A8FE
0x18002a85d  mov     rax, [rbx]
0x18002a860  lea     r12, ?PathExts@@3PAPEAGA; ushort * near * PathExts
0x18002a867  mov     r14d, ebp
0x18002a86a  test    rax, rax
0x18002a86d  jz      short loc_18002A874
0x18002a86f  mov     rdx, [rax]
0x18002a872  jmp     short loc_18002A877
0x18002a874  mov     rdx, r15; lpFileName
0x18002a877  mov     rax, [rdi+40h]
0x18002a87b  test    rax, rax
0x18002a87e  jz      short loc_18002A885
0x18002a880  mov     rcx, [rax]
0x18002a883  jmp     short loc_18002A888
0x18002a885  mov     rcx, r15; lpPath
0x18002a888  mov     r8, [r12+r14*8]; lpExtension
0x18002a88c  lea     rax, [rsp+288h+FilePart]
0x18002a891  mov     [rsp+288h+lpFilePart], rax; lpFilePart
0x18002a896  mov     r9d, 105h; nBufferLength
0x18002a89c  lea     rax, [rsp+288h+Buffer]
0x18002a8a1  mov     [rsp+288h+lpBuffer], rax; lpBuffer
0x18002a8a6  call    cs:__imp_SearchPathW
0x18002a8ac  test    eax, eax
0x18002a8ae  jnz     short loc_18002A8F1
0x18002a8b0  mov     rax, [rbx]
0x18002a8b3  test    rax, rax
0x18002a8b6  jz      short loc_18002A8BD
0x18002a8b8  mov     rdx, [rax]
0x18002a8bb  jmp     short loc_18002A8C0
0x18002a8bd  mov     rdx, r15; lpFileName
0x18002a8c0  mov     r8, [r12+r14*8]; lpExtension
0x18002a8c4  lea     rax, [rsp+288h+FilePart]
0x18002a8c9  mov     [rsp+288h+lpFilePart], rax; lpFilePart
0x18002a8ce  mov     r9d, 105h; nBufferLength
0x18002a8d4  lea     rax, [rsp+288h+Buffer]
0x18002a8d9  xor     ecx, ecx; lpPath
0x18002a8db  mov     [rsp+288h+lpBuffer], rax; lpBuffer
0x18002a8e0  call    cs:__imp_SearchPathW
0x18002a8e6  test    eax, eax
0x18002a8e8  jnz     short loc_18002A8F1
0x18002a8ea  inc     ebp
0x18002a8ec  jmp     loc_18002A851
0x18002a8f1  lea     rdx, [rsp+288h+Buffer]
0x18002a8f6  mov     rcx, rbx
0x18002a8f9  call    ??4_bstr_t@@QEAAAEAV0@PEBG@Z; _bstr_t::operator=(ushort const *)
0x18002a8fe  mov     rax, [rbx]
0x18002a901  test    rax, rax
0x18002a904  jz      short loc_18002A90B
0x18002a906  mov     rcx, [rax]
0x18002a909  jmp     short loc_18002A90E
0x18002a90b  mov     rcx, r15; Str
0x18002a90e  mov     edx, 2Eh ; '.'; Ch
0x18002a913  call    cs:__imp_wcsrchr
0x18002a919  mov     [rsp+288h+FilePart], rax
0x18002a91e  mov     rbx, rax
0x18002a921  test    rax, rax
0x18002a924  jz      loc_18002A818
0x18002a92a  inc     rsi
0x18002a92d  cmp     [rax+rsi*2], r15w
0x18002a932  jnz     short loc_18002A92A
0x18002a934  cmp     rsi, 1
0x18002a938  jz      loc_18002A818
0x18002a93e  lea     rcx, [rax+2]; String1
0x18002a942  lea     rdx, aLnk; "LNK"
0x18002a949  call    cs:__imp__wcsicmp
0x18002a94f  test    eax, eax
0x18002a951  jnz     short loc_18002A972
0x18002a953  lea     rdx, [rsp+288h+FilePart]; unsigned __int16 **
0x18002a958  mov     rcx, rdi; this
0x18002a95b  call    ?ResolveLink@ExeTask@@IEAAJAEAPEAG@Z; ExeTask::ResolveLink(ushort * &)
0x18002a960  test    eax, eax
0x18002a962  js      loc_18002A81D
0x18002a968  cmp     eax, 1
0x18002a96b  jz      short loc_18002A9CD
0x18002a96d  mov     rbx, [rsp+288h+FilePart]
0x18002a972  mov     ebp, 2
0x18002a977  lea     rdx, off_1800BC010; unsigned __int16 **
0x18002a97e  mov     r8d, ebp; int
0x18002a981  lea     rcx, [rbx+2]; String2
0x18002a985  call    ?IsOnList@@YA_NPEBGPEAPEBGH@Z; IsOnList(ushort const *,ushort const * *,int)
0x18002a98a  test    al, al
0x18002a98c  jnz     short loc_18002A9CD
0x18002a98e  lea     r8d, [rbp+1]; int
0x18002a992  lea     rdx, off_1800BC340; unsigned __int16 **
0x18002a999  lea     rcx, [rbx+2]; String2
0x18002a99d  call    ?IsOnList@@YA_NPEBGPEAPEBGH@Z; IsOnList(ushort const *,ushort const * *,int)
0x18002a9a2  test    al, al
0x18002a9a4  jz      short loc_18002A9BB
0x18002a9a6  mov     rcx, rdi; this
0x18002a9a9  call    ?SetBatchLaunchCommand@ExeTask@@IEAAJXZ; ExeTask::SetBatchLaunchCommand(void)
0x18002a9ae  test    eax, eax
0x18002a9b0  js      short loc_18002A9CD
0x18002a9b2  mov     dword ptr [rdi+28h], 1
0x18002a9b9  jmp     short loc_18002A9CD
0x18002a9bb  mov     rdx, rbx; pszAssoc
0x18002a9be  mov     rcx, rdi; this
0x18002a9c1  call    ?ResolveDocRunAssociation@ExeTask@@IEAAJPEBG@Z; ExeTask::ResolveDocRunAssociation(ushort const *)
0x18002a9c6  test    eax, eax
0x18002a9c8  js      short loc_18002A9CD
0x18002a9ca  mov     [rdi+28h], ebp
0x18002a9cd  xor     eax, eax
0x18002a9cf  jmp     loc_18002A81D
```
