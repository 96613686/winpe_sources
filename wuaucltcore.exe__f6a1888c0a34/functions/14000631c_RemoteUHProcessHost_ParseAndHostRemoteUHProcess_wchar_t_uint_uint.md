# RemoteUHProcessHost::ParseAndHostRemoteUHProcess(wchar_t * *,uint,uint)

- ea: `0x14000631c`
- end: `0x140006486`
- name: `?ParseAndHostRemoteUHProcess@RemoteUHProcessHost@@YAJPEAPEA_WII@Z`
- size: `362`
- prototype: `__int64 __fastcall(RemoteUHProcessHost *__hidden this, wchar_t **, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1400080bc`

## callees

- `0x140002ac0`
- `0x140005f84`
- `0x14000631c`
- `0x14000c508`
- `0x14000c80c`
- `0x14001a943`
- `0x14001a9e8`
- `0x14001aa60`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x140006438`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x140006438`

## string_xrefs

- `0x140006401`: `/ClassId`

## pseudocode

```c
__int64 __fastcall RemoteUHProcessHost::ParseAndHostRemoteUHProcess(
        PCNZWCH *this,
        wchar_t **a2,
        __int64 a3,
        __int64 a4)
{
  __int64 v5; // rdx
  int v6; // ebx
  int v8; // edi
  __int64 v9; // rdi
  PCNZWCH v10; // rbx
  int v11; // ebp
  _DWORD *v12; // rax
  __int64 v13; // r8
  __int64 v14; // r9
  int v15; // edi
  const OLECHAR *v16; // rcx
  IID iid; // [rsp+20h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  if ( (int)a3 + 4 >= (unsigned int)a2 )
  {
    v5 = 93;
LABEL_3:
    v6 = -2147024809;
LABEL_4:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UserProcess\\core\\RemoteUHProcessHost.cpp",
      (const char *)(unsigned int)v6,
      iid.Data1);
    return (unsigned int)v6;
  }
  v8 = a3 + 1;
  if ( AsciiStringCompareI(this[(unsigned int)(a3 + 1)], L"/HandlerId", a3, a4, iid.Data1) )
  {
    v5 = 95;
    goto LABEL_3;
  }
  v9 = (unsigned int)(v8 + 1);
  v10 = this[v9];
  if ( !v10 )
  {
    v6 = -2147024809;
LABEL_13:
    v5 = 97;
    goto LABEL_4;
  }
  *(_DWORD *)o__errno_0() = 0;
  v11 = o__wtoi_0(v10);
  v12 = (_DWORD *)o__errno_0();
  if ( *v12 )
  {
    if ( *v12 != 34 )
    {
      v6 = -2147024809;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x50,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\wusafefn\\safemisc.cpp",
        (const char *)0x80070057LL,
        iid.Data1);
      goto LABEL_13;
    }
    v11 = 0;
    v6 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x4E,
           (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\wusafefn\\safemisc.cpp",
           (const char *)0x216,
           iid.Data1);
    if ( v6 < 0 )
      goto LABEL_13;
  }
  v15 = v9 + 1;
  if ( AsciiStringCompareI(this[v15], L"/ClassId", v13, v14, iid.Data1) )
  {
    v5 = 99;
    goto LABEL_3;
  }
  v16 = this[v15 + 1];
  iid = GUID_NULL;
  v6 = IIDFromString(v16, &iid);
  if ( v6 < 0 )
  {
    v5 = 101;
    goto LABEL_4;
  }
  v6 = RunRemoteUHProcess(v11, &iid);
  if ( v6 < 0 )
  {
    v5 = 103;
    goto LABEL_4;
  }
  return 0;
}

```

## disassembly

```asm
0x14000631c  mov     [rsp+arg_8], rbx
0x140006321  push    rbp
0x140006322  push    rsi
0x140006323  push    rdi
0x140006324  sub     rsp, 40h
0x140006328  mov     rax, cs:__security_cookie
0x14000632f  xor     rax, rsp
0x140006332  mov     [rsp+58h+var_28], rax
0x140006337  lea     eax, [r8+4]
0x14000633b  mov     edi, r8d
0x14000633e  mov     rsi, rcx
0x140006341  cmp     eax, edx
0x140006343  jb      short loc_14000636A
0x140006345  mov     edx, 5Dh ; ']'; void *
0x14000634a  mov     ebx, 80070057h
0x14000634f  mov     rcx, [rsp+58h]; this
0x140006354  lea     r8, aCW1SSrcClientU_3; "C:\\__w\\1\\s\\src\\Client\\UserProcess"...
0x14000635b  mov     r9d, ebx; char *
0x14000635e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140006363  mov     eax, ebx
0x140006365  jmp     loc_14000646C
0x14000636a  inc     edi
0x14000636c  lea     rdx, String2; "/HandlerId"
0x140006373  mov     rcx, [rcx+rdi*8]; lpString1
0x140006377  call    ?AsciiStringCompareI@@YAJPEB_W0@Z; AsciiStringCompareI(wchar_t const *,wchar_t const *)
0x14000637c  test    eax, eax
0x14000637e  jz      short loc_140006387
0x140006380  mov     edx, 5Fh ; '_'
0x140006385  jmp     short loc_14000634A
0x140006387  inc     edi
0x140006389  mov     rbx, [rsi+rdi*8]
0x14000638d  test    rbx, rbx
0x140006390  jnz     short loc_140006399
0x140006392  mov     ebx, 80070057h
0x140006397  jmp     short loc_1400063F5
0x140006399  call    _o__errno_0
0x14000639e  mov     rcx, rbx
0x1400063a1  mov     dword ptr [rax], 0
0x1400063a7  call    _o__wtoi_0
0x1400063ac  mov     ebp, eax
0x1400063ae  call    _o__errno_0
0x1400063b3  cmp     dword ptr [rax], 0
0x1400063b6  jz      short loc_1400063FF
0x1400063b8  cmp     dword ptr [rax], 22h ; '"'
0x1400063bb  lea     r8, aCW1SSrcClientL_9; "C:\\__w\\1\\s\\src\\Client\\lib\\wusafe"...
0x1400063c2  mov     rcx, [rsp+58h]; this
0x1400063c7  jz      short loc_1400063DD
0x1400063c9  mov     ebx, 80070057h
0x1400063ce  mov     edx, 50h ; 'P'; void *
0x1400063d3  mov     r9d, ebx; char *
0x1400063d6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400063db  jmp     short loc_1400063F5
0x1400063dd  mov     r9d, 216h; char *
0x1400063e3  mov     edx, 4Eh ; 'N'; void *
0x1400063e8  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1400063ed  xor     ebp, ebp
0x1400063ef  mov     ebx, eax
0x1400063f1  test    eax, eax
0x1400063f3  jns     short loc_1400063FF
0x1400063f5  mov     edx, 61h ; 'a'
0x1400063fa  jmp     loc_14000634F
0x1400063ff  inc     edi
0x140006401  lea     rdx, aClassid; "/ClassId"
0x140006408  mov     rcx, [rsi+rdi*8]; lpString1
0x14000640c  call    ?AsciiStringCompareI@@YAJPEB_W0@Z; AsciiStringCompareI(wchar_t const *,wchar_t const *)
0x140006411  test    eax, eax
0x140006413  jz      short loc_14000641F
0x140006415  mov     edx, 63h ; 'c'
0x14000641a  jmp     loc_14000634A
0x14000641f  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x140006426  lea     eax, [rdi+1]
0x140006429  mov     rcx, [rsi+rax*8]; lpsz
0x14000642d  lea     rdx, [rsp+58h+iid]; lpiid
0x140006432  movdqu  xmmword ptr [rsp+58h+iid.Data1], xmm0
0x140006438  call    cs:__imp_IIDFromString
0x14000643e  mov     ebx, eax
0x140006440  test    eax, eax
0x140006442  jns     short loc_14000644E
0x140006444  mov     edx, 65h ; 'e'
0x140006449  jmp     loc_14000634F
0x14000644e  lea     rdx, [rsp+58h+iid]
0x140006453  mov     ecx, ebp
0x140006455  call    RunRemoteUHProcess
0x14000645a  mov     ebx, eax
0x14000645c  test    eax, eax
0x14000645e  jns     short loc_14000646A
0x140006460  mov     edx, 67h ; 'g'
0x140006465  jmp     loc_14000634F
0x14000646a  xor     eax, eax
0x14000646c  mov     rcx, [rsp+58h+var_28]
0x140006471  xor     rcx, rsp; StackCookie
0x140006474  call    __security_check_cookie
0x140006479  mov     rbx, [rsp+58h+arg_8]
0x14000647e  add     rsp, 40h
0x140006482  pop     rdi
0x140006483  pop     rsi
0x140006484  pop     rbp
0x140006485  retn
```
