# UndockedComponentInfo::ToString(wchar_t * *)

- ea: `0x18000e864`
- end: `0x18000e956`
- name: `?ToString@UndockedComponentInfo@@QEAAJPEAPEA_W@Z`
- size: `242`
- prototype: `__int64 __fastcall(UndockedComponentInfo *__hidden this, wchar_t **)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180005524`

## callees

- `0x180001ca8`
- `0x180003760`
- `0x18000ab44`
- `0x18000e864`
- `0x18000fc90`
- `0x180015a30`

## string_xrefs

- `0x18000e8d3`: `UusId:%s|hr:0x%x|ModuleVer:%ws|LoadProps:%lu|Path:%ws`

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
0x18000e864  mov     [rsp+arg_10], rbx
0x18000e869  mov     [rsp+arg_18], rsi
0x18000e86e  push    rdi
0x18000e86f  sub     rsp, 860h
0x18000e876  mov     rax, cs:__security_cookie
0x18000e87d  xor     rax, rsp
0x18000e880  mov     [rsp+868h+var_18], rax
0x18000e888  mov     rdi, rdx
0x18000e88b  mov     rbx, rcx
0x18000e88e  xor     esi, esi
0x18000e890  lea     rcx, [rsp+868h+var_826]; void *
0x18000e895  xor     edx, edx; Val
0x18000e897  mov     [rsp+868h+Buffer], si
0x18000e89c  mov     r8d, 800h; Size
0x18000e8a2  call    memset
0x18000e8a7  test    rdi, rdi
0x18000e8aa  jnz     short loc_18000E8CF
0x18000e8ac  mov     ebx, 80004003h
0x18000e8b1  lea     edx, [rsi+23h]; void *
0x18000e8b4  mov     rcx, [rsp+868h]; this
0x18000e8bc  lea     r8, aCW1SSrcClientL_2; "C:\\__w\\1\\s\\src\\Client\\lib\\Undock"...
0x18000e8c3  mov     r9d, ebx; char *
0x18000e8c6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e8cb  mov     eax, ebx
0x18000e8cd  jmp     short loc_18000E931
0x18000e8cf  mov     rax, [rbx+10h]
0x18000e8d3  lea     r8, aUusidSHr0xXMod; "UusId:%s|hr:0x%x|ModuleVer:%ws|LoadProp"...
0x18000e8da  mov     r9, [rbx+8]
0x18000e8de  lea     rcx, [rsp+868h+Buffer]; Buffer
0x18000e8e3  mov     [rsp+868h+var_830], rax
0x18000e8e8  mov     edx, 401h; unsigned __int64
0x18000e8ed  mov     eax, [rbx+4]
0x18000e8f0  mov     [rsp+868h+var_838], eax
0x18000e8f4  mov     rax, [rbx+18h]
0x18000e8f8  mov     [rsp+868h+var_840], rax
0x18000e8fd  mov     eax, [rbx]
0x18000e8ff  mov     [rsp+868h+var_848], eax
0x18000e903  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x18000e908  mov     ebx, eax
0x18000e90a  test    eax, eax
0x18000e90c  jns     short loc_18000E915
0x18000e90e  mov     edx, 2Ch ; ','
0x18000e913  jmp     short loc_18000E8B4
0x18000e915  mov     rdx, rdi
0x18000e918  lea     rcx, [rsp+868h+Buffer]
0x18000e91d  call    ??$DuplicateString@PEA_WPEA_W@@YAJPEA_WPEAPEA_W@Z; DuplicateString<wchar_t *,wchar_t *>(wchar_t *,wchar_t * *)
0x18000e922  mov     ebx, eax
0x18000e924  test    eax, eax
0x18000e926  jns     short loc_18000E92F
0x18000e928  mov     edx, 2Eh ; '.'
0x18000e92d  jmp     short loc_18000E8B4
0x18000e92f  xor     eax, eax
0x18000e931  mov     rcx, [rsp+868h+var_18]
0x18000e939  xor     rcx, rsp; StackCookie
0x18000e93c  call    __security_check_cookie
0x18000e941  lea     r11, [rsp+868h+var_8]
0x18000e949  mov     rbx, [r11+20h]
0x18000e94d  mov     rsi, [r11+28h]
0x18000e951  mov     rsp, r11
0x18000e954  pop     rdi
0x18000e955  retn
```
