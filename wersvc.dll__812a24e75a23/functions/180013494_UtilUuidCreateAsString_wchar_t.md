# UtilUuidCreateAsString(wchar_t *)

- ea: `0x180013494`
- end: `0x18001353f`
- name: `?UtilUuidCreateAsString@@YAJPEA_W@Z`
- size: `171`
- prototype: `__int64 __fastcall(wchar_t *)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800101dc`
- `0x180012e94`

## callees

- `0x1800029d0`
- `0x180007a14`
- `0x18000cb10`
- `0x180013494`

## import_xrefs

- `RPCRT4!UuidCreate` at `0x1800134e4`
- `RPCRT4!UuidCreate` at `0x1800134e4`

## string_xrefs

- `0x1800134c4`: `onecore\windows\feedback\core\common\lib\utilitydownlevel.cpp`

## pseudocode

```c
__int64 __fastcall UtilUuidCreateAsString(wchar_t *a1)
{
  unsigned int v2; // ebx
  __int64 v3; // rdx
  RPC_STATUS v5; // eax
  __int64 v6; // r8
  UUID Uuid; // [rsp+20h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  if ( !a1 )
  {
    v2 = -2147024809;
    v3 = 1396;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v3,
      (int)"onecore\\windows\\feedback\\core\\common\\lib\\utilitydownlevel.cpp",
      (const char *)v2);
    return v2;
  }
  Uuid = 0;
  v5 = UuidCreate(&Uuid);
  v2 = v5;
  if ( v5 && v5 != 1824 )
  {
    if ( v5 > 0 )
      v2 = (unsigned __int16)v5 | 0x80070000;
    v3 = 1402;
    if ( (v2 & 0x80000000) == 0 )
      v2 = -2147467259;
    goto LABEL_3;
  }
  LOBYTE(v6) = 1;
  tlx::guid_to_string_lower<wchar_t>(a1, &Uuid, v6);
  return 0;
}

```

## disassembly

```asm
0x180013494  mov     [rsp+arg_8], rbx
0x180013499  push    rdi
0x18001349a  sub     rsp, 40h
0x18001349e  mov     rax, cs:__security_cookie
0x1800134a5  xor     rax, rsp
0x1800134a8  mov     [rsp+48h+var_18], rax
0x1800134ad  mov     rdi, rcx
0x1800134b0  test    rcx, rcx
0x1800134b3  jnz     short loc_1800134D7
0x1800134b5  mov     ebx, 80070057h
0x1800134ba  mov     edx, 574h; void *
0x1800134bf  mov     rcx, [rsp+48h]; this
0x1800134c4  lea     r8, aOnecoreWindows_0; "onecore\\windows\\feedback\\core\\commo"...
0x1800134cb  mov     r9d, ebx; char *
0x1800134ce  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800134d3  mov     eax, ebx
0x1800134d5  jmp     short loc_180013527
0x1800134d7  xorps   xmm0, xmm0
0x1800134da  lea     rcx, [rsp+48h+Uuid]; Uuid
0x1800134df  movups  xmmword ptr [rsp+48h+Uuid.Data1], xmm0
0x1800134e4  call    cs:__imp_UuidCreate
0x1800134ea  mov     ebx, eax
0x1800134ec  test    eax, eax
0x1800134ee  jz      short loc_180013515
0x1800134f0  cmp     eax, 720h
0x1800134f5  jz      short loc_180013515
0x1800134f7  test    eax, eax
0x1800134f9  jle     short loc_180013504
0x1800134fb  movzx   ebx, ax
0x1800134fe  or      ebx, 80070000h
0x180013504  test    ebx, ebx
0x180013506  mov     eax, 80004005h
0x18001350b  mov     edx, 57Ah
0x180013510  cmovns  ebx, eax
0x180013513  jmp     short loc_1800134BF
0x180013515  mov     r8b, 1
0x180013518  lea     rdx, [rsp+48h+Uuid]
0x18001351d  mov     rcx, rdi
0x180013520  call    ??$guid_to_string_lower@_W@tlx@@YAXPEA_WAEBU_GUID@@_N@Z; tlx::guid_to_string_lower<wchar_t>(wchar_t *,_GUID const &,bool)
0x180013525  xor     eax, eax
0x180013527  mov     rcx, [rsp+48h+var_18]
0x18001352c  xor     rcx, rsp; StackCookie
0x18001352f  call    __security_check_cookie
0x180013534  mov     rbx, [rsp+48h+arg_8]
0x180013539  add     rsp, 40h
0x18001353d  pop     rdi
0x18001353e  retn
```
