# LoadStr(ushort * *,uint)

- ea: `0x1400146ac`
- end: `0x140014779`
- name: `?LoadStr@@YAHPEAPEAGI@Z`
- size: `205`
- prototype: `__int64 __fastcall(unsigned __int16 **, unsigned int)`
- caller_count: `10`
- callee_count: `3`
- tags: ``

## callers

- `0x140005740`
- `0x1400057f0`
- `0x140005990`
- `0x140005ab0`
- `0x140005ce0`
- `0x140008764`
- `0x14000a098`
- `0x14000a568`
- `0x14000eedc`
- `0x140011e90`

## callees

- `0x1400146ac`
- `0x1400175a0`
- `0x1400175d0`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x140014748`
- `OLEAUT32!__imp_SysAllocString` at `0x140014748`
- `KERNEL32!MultiByteToWideChar` at `0x140014734`
- `KERNEL32!MultiByteToWideChar` at `0x140014734`
- `USER32!LoadStringA` at `0x140014708`
- `USER32!LoadStringA` at `0x140014708`
- `USER32!LoadStringW` at `0x1400146f9`
- `USER32!LoadStringW` at `0x1400146f9`

## pseudocode

```c
unsigned __int16 *__fastcall LoadStr(unsigned __int16 **a1, UINT a2)
{
  bool v2; // zf
  int StringW; // eax
  unsigned int v5; // ebx
  unsigned __int16 *result; // rax
  CHAR MultiByteStr[2048]; // [rsp+30h] [rbp-1818h] BYREF
  WCHAR Buffer[2048]; // [rsp+830h] [rbp-1018h] BYREF

  v2 = !Global::g_fWindowsNT;
  *a1 = 0;
  if ( v2 )
  {
    v5 = 0;
    if ( !LoadStringA(Global::g_hResource, a2, MultiByteStr, 2048) )
      return (unsigned __int16 *)v5;
    StringW = MultiByteToWideChar(0, 0, MultiByteStr, -1, Buffer, 2048);
  }
  else
  {
    StringW = LoadStringW(Global::g_hResource, a2, Buffer, 2048);
  }
  v5 = StringW;
  if ( !StringW )
    return (unsigned __int16 *)v5;
  result = SysAllocString(Buffer);
  *a1 = result;
  if ( result )
    return (unsigned __int16 *)v5;
  return result;
}

```

## disassembly

```asm
0x1400146ac  mov     [rsp+arg_10], rbx
0x1400146b1  push    rdi
0x1400146b2  mov     eax, 1840h
0x1400146b7  call    _alloca_probe
0x1400146bc  sub     rsp, rax
0x1400146bf  mov     rax, cs:__security_cookie
0x1400146c6  xor     rax, rsp
0x1400146c9  mov     [rsp+1848h+var_18], rax
0x1400146d1  cmp     cs:?g_fWindowsNT@Global@@2_NA, 0; bool Global::g_fWindowsNT
0x1400146d8  mov     rdi, rcx
0x1400146db  mov     qword ptr [rcx], 0
0x1400146e2  mov     r9d, 800h; cchBufferMax
0x1400146e8  mov     rcx, cs:?g_hResource@Global@@2PEAUHINSTANCE__@@EA; hInstance
0x1400146ef  jz      short loc_140014701
0x1400146f1  lea     r8, [rsp+1848h+Buffer]; lpBuffer
0x1400146f9  call    cs:__imp_LoadStringW
0x1400146ff  jmp     short loc_14001473A
0x140014701  lea     r8, [rsp+1848h+MultiByteStr]; lpBuffer
0x140014706  xor     ebx, ebx
0x140014708  call    cs:__imp_LoadStringA
0x14001470e  test    eax, eax
0x140014710  jz      short loc_140014756
0x140014712  lea     rax, [rsp+1848h+Buffer]
0x14001471a  mov     [rsp+1848h+cchWideChar], 800h; cchWideChar
0x140014722  or      r9d, 0FFFFFFFFh; cbMultiByte
0x140014726  mov     [rsp+1848h+lpWideCharStr], rax; lpWideCharStr
0x14001472b  lea     r8, [rsp+1848h+MultiByteStr]; lpMultiByteStr
0x140014730  xor     edx, edx; dwFlags
0x140014732  xor     ecx, ecx; CodePage
0x140014734  call    cs:__imp_MultiByteToWideChar
0x14001473a  mov     ebx, eax
0x14001473c  test    eax, eax
0x14001473e  jz      short loc_140014756
0x140014740  lea     rcx, [rsp+1848h+Buffer]; psz
0x140014748  call    cs:__imp_SysAllocString
0x14001474e  mov     [rdi], rax
0x140014751  test    rax, rax
0x140014754  jz      short loc_140014758
0x140014756  mov     eax, ebx
0x140014758  mov     rcx, [rsp+1848h+var_18]
0x140014760  xor     rcx, rsp; StackCookie
0x140014763  call    __security_check_cookie
0x140014768  mov     rbx, [rsp+1848h+arg_10]
0x140014770  add     rsp, 1840h
0x140014777  pop     rdi
0x140014778  retn
```
