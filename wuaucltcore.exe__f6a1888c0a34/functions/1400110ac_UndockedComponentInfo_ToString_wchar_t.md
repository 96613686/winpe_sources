# UndockedComponentInfo::ToString(wchar_t * *)

- ea: `0x1400110ac`
- end: `0x14001119e`
- name: `?ToString@UndockedComponentInfo@@QEAAJPEAPEA_W@Z`
- size: `242`
- prototype: `__int64 __fastcall(UndockedComponentInfo *__hidden this, wchar_t **)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400074c8`

## callees

- `0x140002ac0`
- `0x140002d48`
- `0x14000cae4`
- `0x1400110ac`
- `0x14001aa60`
- `0x140020760`

## string_xrefs

- `0x14001111b`: `UusId:%s|hr:0x%x|ModuleVer:%ws|LoadProps:%lu|Path:%ws`

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
0x1400110ac  mov     [rsp+arg_10], rbx
0x1400110b1  mov     [rsp+arg_18], rsi
0x1400110b6  push    rdi
0x1400110b7  sub     rsp, 860h
0x1400110be  mov     rax, cs:__security_cookie
0x1400110c5  xor     rax, rsp
0x1400110c8  mov     [rsp+868h+var_18], rax
0x1400110d0  mov     rdi, rdx
0x1400110d3  mov     rbx, rcx
0x1400110d6  xor     esi, esi
0x1400110d8  lea     rcx, [rsp+868h+var_826]; void *
0x1400110dd  xor     edx, edx; Val
0x1400110df  mov     [rsp+868h+Buffer], si
0x1400110e4  mov     r8d, 800h; Size
0x1400110ea  call    memset
0x1400110ef  test    rdi, rdi
0x1400110f2  jnz     short loc_140011117
0x1400110f4  mov     ebx, 80004003h
0x1400110f9  lea     edx, [rsi+23h]; void *
0x1400110fc  mov     rcx, [rsp+868h]; this
0x140011104  lea     r8, aCW1SSrcClientL_2; "C:\\__w\\1\\s\\src\\Client\\lib\\Undock"...
0x14001110b  mov     r9d, ebx; char *
0x14001110e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140011113  mov     eax, ebx
0x140011115  jmp     short loc_140011179
0x140011117  mov     rax, [rbx+10h]
0x14001111b  lea     r8, aUusidSHr0xXMod; "UusId:%s|hr:0x%x|ModuleVer:%ws|LoadProp"...
0x140011122  mov     r9, [rbx+8]
0x140011126  lea     rcx, [rsp+868h+Buffer]; Buffer
0x14001112b  mov     [rsp+868h+var_830], rax
0x140011130  mov     edx, 401h; unsigned __int64
0x140011135  mov     eax, [rbx+4]
0x140011138  mov     [rsp+868h+var_838], eax
0x14001113c  mov     rax, [rbx+18h]
0x140011140  mov     [rsp+868h+var_840], rax
0x140011145  mov     eax, [rbx]
0x140011147  mov     [rsp+868h+var_848], eax
0x14001114b  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x140011150  mov     ebx, eax
0x140011152  test    eax, eax
0x140011154  jns     short loc_14001115D
0x140011156  mov     edx, 2Ch ; ','
0x14001115b  jmp     short loc_1400110FC
0x14001115d  mov     rdx, rdi
0x140011160  lea     rcx, [rsp+868h+Buffer]
0x140011165  call    ??$DuplicateString@PEA_WPEA_W@@YAJPEA_WPEAPEA_W@Z; DuplicateString<wchar_t *,wchar_t *>(wchar_t *,wchar_t * *)
0x14001116a  mov     ebx, eax
0x14001116c  test    eax, eax
0x14001116e  jns     short loc_140011177
0x140011170  mov     edx, 2Eh ; '.'
0x140011175  jmp     short loc_1400110FC
0x140011177  xor     eax, eax
0x140011179  mov     rcx, [rsp+868h+var_18]
0x140011181  xor     rcx, rsp; StackCookie
0x140011184  call    __security_check_cookie
0x140011189  lea     r11, [rsp+868h+var_8]
0x140011191  mov     rbx, [r11+20h]
0x140011195  mov     rsi, [r11+28h]
0x140011199  mov     rsp, r11
0x14001119c  pop     rdi
0x14001119d  retn
```
