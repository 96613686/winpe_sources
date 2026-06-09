# UndockedComponentInfo::ToString(wchar_t * *)

- ea: `0x18000d6f8`
- end: `0x18000d7ea`
- name: `?ToString@UndockedComponentInfo@@QEAAJPEAPEA_W@Z`
- size: `242`
- prototype: `__int64 __fastcall(UndockedComponentInfo *__hidden this, wchar_t **)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180003128`

## callees

- `0x180005d80`
- `0x180006858`
- `0x18000d6f8`
- `0x18000e0fc`
- `0x18000ed40`
- `0x1800154b0`

## string_xrefs

- `0x18000d767`: `UusId:%s|hr:0x%x|ModuleVer:%ws|LoadProps:%lu|Path:%ws`

## pseudocode

```c
__int64 __fastcall UndockedComponentInfo::ToString(UndockedComponentInfo *this, wchar_t **a2)
{
  int v3; // ebx
  __int64 v4; // rdx
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
      (int)"C:\\__w\\1\\s\\src\\Client\\lib\\UndockingTelemetry\\UndockingTelemetry.cpp",
      (const char *)(unsigned int)v3);
    return (unsigned int)v3;
  }
  v3 = StringCchPrintfW(
         Buffer,
         1025,
         L"UusId:%s|hr:0x%x|ModuleVer:%ws|LoadProps:%lu|Path:%ws",
         *((_QWORD *)this + 1),
         *(_DWORD *)this,
         *((_QWORD *)this + 3),
         *((_DWORD *)this + 1),
         *((_QWORD *)this + 2));
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
0x18000d6f8  mov     [rsp+arg_10], rbx
0x18000d6fd  mov     [rsp+arg_18], rsi
0x18000d702  push    rdi
0x18000d703  sub     rsp, 860h
0x18000d70a  mov     rax, cs:__security_cookie
0x18000d711  xor     rax, rsp
0x18000d714  mov     [rsp+868h+var_18], rax
0x18000d71c  mov     rdi, rdx
0x18000d71f  mov     rbx, rcx
0x18000d722  xor     esi, esi
0x18000d724  lea     rcx, [rsp+868h+var_826]; void *
0x18000d729  xor     edx, edx; Val
0x18000d72b  mov     [rsp+868h+Buffer], si
0x18000d730  mov     r8d, 800h; Size
0x18000d736  call    memset
0x18000d73b  test    rdi, rdi
0x18000d73e  jnz     short loc_18000D763
0x18000d740  mov     ebx, 80004003h
0x18000d745  lea     edx, [rsi+23h]; void *
0x18000d748  mov     rcx, [rsp+868h]; this
0x18000d750  lea     r8, aCW1SSrcClientL_1; "C:\\__w\\1\\s\\src\\Client\\lib\\Undock"...
0x18000d757  mov     r9d, ebx; char *
0x18000d75a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d75f  mov     eax, ebx
0x18000d761  jmp     short loc_18000D7C5
0x18000d763  mov     rax, [rbx+10h]
0x18000d767  lea     r8, aUusidSHr0xXMod; "UusId:%s|hr:0x%x|ModuleVer:%ws|LoadProp"...
0x18000d76e  mov     r9, [rbx+8]
0x18000d772  lea     rcx, [rsp+868h+Buffer]; Buffer
0x18000d777  mov     [rsp+868h+var_830], rax
0x18000d77c  mov     edx, 401h; unsigned __int64
0x18000d781  mov     eax, [rbx+4]
0x18000d784  mov     [rsp+868h+var_838], eax
0x18000d788  mov     rax, [rbx+18h]
0x18000d78c  mov     [rsp+868h+var_840], rax
0x18000d791  mov     eax, [rbx]
0x18000d793  mov     [rsp+868h+var_848], eax
0x18000d797  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x18000d79c  mov     ebx, eax
0x18000d79e  test    eax, eax
0x18000d7a0  jns     short loc_18000D7A9
0x18000d7a2  mov     edx, 2Ch ; ','
0x18000d7a7  jmp     short loc_18000D748
0x18000d7a9  mov     rdx, rdi
0x18000d7ac  lea     rcx, [rsp+868h+Buffer]
0x18000d7b1  call    ??$DuplicateString@PEA_WPEA_W@@YAJPEA_WPEAPEA_W@Z; DuplicateString<wchar_t *,wchar_t *>(wchar_t *,wchar_t * *)
0x18000d7b6  mov     ebx, eax
0x18000d7b8  test    eax, eax
0x18000d7ba  jns     short loc_18000D7C3
0x18000d7bc  mov     edx, 2Eh ; '.'
0x18000d7c1  jmp     short loc_18000D748
0x18000d7c3  xor     eax, eax
0x18000d7c5  mov     rcx, [rsp+868h+var_18]
0x18000d7cd  xor     rcx, rsp; StackCookie
0x18000d7d0  call    __security_check_cookie
0x18000d7d5  lea     r11, [rsp+868h+var_8]
0x18000d7dd  mov     rbx, [r11+20h]
0x18000d7e1  mov     rsi, [r11+28h]
0x18000d7e5  mov     rsp, r11
0x18000d7e8  pop     rdi
0x18000d7e9  retn
```
