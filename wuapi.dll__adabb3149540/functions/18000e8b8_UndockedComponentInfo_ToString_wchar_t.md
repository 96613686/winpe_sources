# UndockedComponentInfo::ToString(wchar_t * *)

- ea: `0x18000e8b8`
- end: `0x18000e9aa`
- name: `?ToString@UndockedComponentInfo@@QEAAJPEAPEA_W@Z`
- size: `242`
- prototype: `__int64 __fastcall(UndockedComponentInfo *__hidden this, wchar_t **)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180007308`

## callees

- `0x180001ca8`
- `0x180003760`
- `0x18000ab98`
- `0x18000e8b8`
- `0x18000fce0`
- `0x180015a80`

## string_xrefs

- `0x18000e927`: `UusId:%s|hr:0x%x|ModuleVer:%ws|LoadProps:%lu|Path:%ws`

## pseudocode

```c
__int64 __fastcall UndockedComponentInfo::ToString(UndockedComponentInfo *this, wchar_t **a2)
{
  int v3; // ebx
  __int64 v4; // rdx
  int v6; // [rsp+20h] [rbp-848h]
  wchar_t Buffer[1032]; // [rsp+40h] [rbp-828h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+868h] [rbp+0h]

  memset(Buffer, 0, 2050);
  if ( !a2 )
  {
    v3 = -2147467261;
    v4 = 35;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v4,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\UndockingTelemetry\\UndockingTelemetry.cpp",
      (const char *)(unsigned int)v3,
      v6);
    return (unsigned int)v3;
  }
  v6 = *(_DWORD *)this;
  v3 = StringCchPrintfW(Buffer, 0x401u, L"UusId:%s|hr:0x%x|ModuleVer:%ws|LoadProps:%lu|Path:%ws", *((_QWORD *)this + 1));
  if ( v3 < 0 )
  {
    v4 = 44;
    goto LABEL_3;
  }
  v3 = DuplicateString<wchar_t *,wchar_t *>(Buffer, a2);
  if ( v3 < 0 )
  {
    v4 = 46;
    goto LABEL_3;
  }
  return 0;
}

```

## disassembly

```asm
0x18000e8b8  mov     [rsp+arg_10], rbx
0x18000e8bd  mov     [rsp+arg_18], rsi
0x18000e8c2  push    rdi
0x18000e8c3  sub     rsp, 860h
0x18000e8ca  mov     rax, cs:__security_cookie
0x18000e8d1  xor     rax, rsp
0x18000e8d4  mov     [rsp+868h+var_18], rax
0x18000e8dc  mov     rdi, rdx
0x18000e8df  mov     rbx, rcx
0x18000e8e2  xor     esi, esi
0x18000e8e4  lea     rcx, [rsp+868h+var_826]; void *
0x18000e8e9  xor     edx, edx; Val
0x18000e8eb  mov     [rsp+868h+Buffer], si
0x18000e8f0  mov     r8d, 800h; Size
0x18000e8f6  call    memset
0x18000e8fb  test    rdi, rdi
0x18000e8fe  jnz     short loc_18000E923
0x18000e900  mov     ebx, 80004003h
0x18000e905  lea     edx, [rsi+23h]; void *
0x18000e908  mov     rcx, [rsp+868h]; this
0x18000e910  lea     r8, aCW1SSrcClientL_2; "C:\\__w\\1\\s\\src\\Client\\lib\\Undock"...
0x18000e917  mov     r9d, ebx; char *
0x18000e91a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e91f  mov     eax, ebx
0x18000e921  jmp     short loc_18000E985
0x18000e923  mov     rax, [rbx+10h]
0x18000e927  lea     r8, aUusidSHr0xXMod; "UusId:%s|hr:0x%x|ModuleVer:%ws|LoadProp"...
0x18000e92e  mov     r9, [rbx+8]
0x18000e932  lea     rcx, [rsp+868h+Buffer]; Buffer
0x18000e937  mov     [rsp+868h+var_830], rax
0x18000e93c  mov     edx, 401h; unsigned __int64
0x18000e941  mov     eax, [rbx+4]
0x18000e944  mov     [rsp+868h+var_838], eax
0x18000e948  mov     rax, [rbx+18h]
0x18000e94c  mov     [rsp+868h+var_840], rax
0x18000e951  mov     eax, [rbx]
0x18000e953  mov     [rsp+868h+var_848], eax
0x18000e957  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x18000e95c  mov     ebx, eax
0x18000e95e  test    eax, eax
0x18000e960  jns     short loc_18000E969
0x18000e962  mov     edx, 2Ch ; ','
0x18000e967  jmp     short loc_18000E908
0x18000e969  mov     rdx, rdi
0x18000e96c  lea     rcx, [rsp+868h+Buffer]
0x18000e971  call    ??$DuplicateString@PEA_WPEA_W@@YAJPEA_WPEAPEA_W@Z; DuplicateString<wchar_t *,wchar_t *>(wchar_t *,wchar_t * *)
0x18000e976  mov     ebx, eax
0x18000e978  test    eax, eax
0x18000e97a  jns     short loc_18000E983
0x18000e97c  mov     edx, 2Eh ; '.'
0x18000e981  jmp     short loc_18000E908
0x18000e983  xor     eax, eax
0x18000e985  mov     rcx, [rsp+868h+var_18]
0x18000e98d  xor     rcx, rsp; StackCookie
0x18000e990  call    __security_check_cookie
0x18000e995  lea     r11, [rsp+868h+var_8]
0x18000e99d  mov     rbx, [r11+20h]
0x18000e9a1  mov     rsi, [r11+28h]
0x18000e9a5  mov     rsp, r11
0x18000e9a8  pop     rdi
0x18000e9a9  retn
```
