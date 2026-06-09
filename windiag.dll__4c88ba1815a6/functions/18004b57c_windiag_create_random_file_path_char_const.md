# windiag::create_random_file_path(char const *)

- ea: `0x18004b57c`
- end: `0x18004b735`
- name: `?create_random_file_path@windiag@@YA?AV?$optional@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@std@@PEBD@Z`
- size: `441`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `3`
- callee_count: `9`
- tags: ``

## callers

- `0x180047ed8`
- `0x18004d124`
- `0x18005ede8`

## callees

- `0x180004510`
- `0x1800054e4`
- `0x180005520`
- `0x18003af08`
- `0x18003b0bc`
- `0x180041e58`
- `0x180042ba8`
- `0x18004b57c`
- `0x18004faec`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004b5d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004b5d9`
- `RPCRT4!UuidCreate` at `0x18004b5f4`
- `RPCRT4!UuidCreate` at `0x18004b5f4`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x18004b5cf`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x18004b5cf`

## string_xrefs

- `0x18004b705`: `create_random_file_path`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall windiag::create_random_file_path(__int64 a1)
{
  DWORD LastError; // eax
  _QWORD *v3; // rbx
  __int64 v4; // rax
  __int64 v5; // rax
  __int64 v6; // rax
  _QWORD v8[4]; // [rsp+38h] [rbp-C8h] BYREF
  char v9; // [rsp+58h] [rbp-A8h]
  UUID Uuid; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v11[32]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v12[32]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v13[32]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE pExceptionObject[1072]; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v15[528]; // [rsp+500h] [rbp+400h] BYREF

  *(_QWORD *)&Uuid.Data1 = a1;
  memset_0(v15, 0, 0x20Au);
  if ( !(unsigned int)GetTempPath2W(260, v15) )
  {
    LastError = GetLastError();
    if ( LastError )
    {
      windiag::system_exception::system_exception(
        (windiag::system_exception *)pExceptionObject,
        LastError,
        0,
        "[%s:%d] failed; ",
        "create_random_file_path",
        471);
      throw (windiag::system_exception *)pExceptionObject;
    }
  }
  Uuid = 0;
  if ( UuidCreate(&Uuid) || (windiag::guid_to_string(v8, &Uuid), !v9) )
  {
    *(_BYTE *)(a1 + 32) = 0;
  }
  else
  {
    v3 = v8;
    if ( v8[3] > 0xFu )
      v3 = (_QWORD *)v8[0];
    v4 = windiag::wchar_to_string(v13, v15);
    v5 = std::operator+<char>(v12, v4, v3);
    v6 = std::operator+<char>(v11, v5, ".etl");
    *(_OWORD *)a1 = 0;
    *(_QWORD *)(a1 + 16) = 0;
    *(_QWORD *)(a1 + 24) = 0;
    *(_OWORD *)a1 = *(_OWORD *)v6;
    *(_OWORD *)(a1 + 16) = *(_OWORD *)(v6 + 16);
    *(_QWORD *)(v6 + 16) = 0;
    *(_QWORD *)(v6 + 24) = 15;
    *(_BYTE *)v6 = 0;
    *(_BYTE *)(a1 + 32) = 1;
    std::string::~string(v11);
    std::string::~string(v12);
    std::string::~string(v13);
    if ( v9 )
      std::string::~string(v8);
  }
  return a1;
}

```

## disassembly

```asm
0x18004b57c  mov     [rsp-8+arg_8], rbx
0x18004b581  mov     [rsp-8+arg_10], rdi
0x18004b586  push    rbp
0x18004b587  lea     rbp, [rsp-620h]
0x18004b58f  sub     rsp, 720h
0x18004b596  mov     rax, cs:__security_cookie
0x18004b59d  xor     rax, rsp
0x18004b5a0  mov     [rbp+620h+var_10], rax
0x18004b5a7  mov     rdi, rcx
0x18004b5aa  mov     qword ptr [rsp+720h+Uuid.Data1], rcx
0x18004b5af  xor     edx, edx; Val
0x18004b5b1  mov     r8d, 20Ah; Size
0x18004b5b7  lea     rcx, [rbp+620h+var_220]; void *
0x18004b5be  call    memset_0
0x18004b5c3  lea     rdx, [rbp+620h+var_220]
0x18004b5ca  mov     ecx, 104h
0x18004b5cf  call    cs:__imp_GetTempPath2W
0x18004b5d5  test    eax, eax
0x18004b5d7  jnz     short loc_18004B5E7
0x18004b5d9  call    cs:__imp_GetLastError
0x18004b5df  test    eax, eax
0x18004b5e1  jnz     loc_18004B6FB
0x18004b5e7  xorps   xmm0, xmm0
0x18004b5ea  movups  xmmword ptr [rsp+720h+Uuid.Data1], xmm0
0x18004b5ef  lea     rcx, [rsp+720h+Uuid]; Uuid
0x18004b5f4  call    cs:__imp_UuidCreate
0x18004b5fa  test    eax, eax
0x18004b5fc  jnz     loc_18004B6D0
0x18004b602  lea     rdx, [rsp+720h+Uuid]
0x18004b607  lea     rcx, [rsp+720h+var_6E8]
0x18004b60c  call    ?guid_to_string@windiag@@YA?AV?$optional@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@std@@AEBU_GUID@@@Z; windiag::guid_to_string(_GUID const &)
0x18004b611  nop
0x18004b612  cmp     [rsp+720h+var_6C8], 0
0x18004b617  jz      loc_18004B6D0
0x18004b61d  lea     rbx, [rsp+720h+var_6E8]
0x18004b622  cmp     [rsp+720h+var_6D0], 0Fh
0x18004b628  cmova   rbx, [rsp+720h+var_6E8]
0x18004b62e  lea     rdx, [rbp+620h+var_220]
0x18004b635  lea     rcx, [rbp+620h+var_670]
0x18004b639  call    ?wchar_to_string@windiag@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEBG@Z; windiag::wchar_to_string(ushort const *)
0x18004b63e  nop
0x18004b63f  mov     r8, rbx
0x18004b642  mov     rdx, rax
0x18004b645  lea     rcx, [rbp+620h+var_690]
0x18004b649  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@$$QEAV10@QEBD@Z; std::operator+<char>(std::string &&,char const * const)
0x18004b64e  nop
0x18004b64f  lea     r8, aEtl; ".etl"
0x18004b656  mov     rdx, rax
0x18004b659  lea     rcx, [rsp+720h+var_6B0]
0x18004b65e  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@$$QEAV10@QEBD@Z; std::operator+<char>(std::string &&,char const * const)
0x18004b663  xorps   xmm0, xmm0
0x18004b666  movups  xmmword ptr [rdi], xmm0
0x18004b669  mov     qword ptr [rdi+10h], 0
0x18004b671  mov     qword ptr [rdi+18h], 0
0x18004b679  movups  xmm0, xmmword ptr [rax]
0x18004b67c  movups  xmmword ptr [rdi], xmm0
0x18004b67f  movups  xmm1, xmmword ptr [rax+10h]
0x18004b683  movups  xmmword ptr [rdi+10h], xmm1
0x18004b687  mov     qword ptr [rax+10h], 0
0x18004b68f  mov     qword ptr [rax+18h], 0Fh
0x18004b697  mov     byte ptr [rax], 0
0x18004b69a  mov     byte ptr [rdi+20h], 1
0x18004b69e  lea     rcx, [rsp+720h+var_6B0]
0x18004b6a3  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18004b6a8  nop
0x18004b6a9  lea     rcx, [rbp+620h+var_690]
0x18004b6ad  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18004b6b2  nop
0x18004b6b3  lea     rcx, [rbp+620h+var_670]
0x18004b6b7  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18004b6bc  nop
0x18004b6bd  cmp     [rsp+720h+var_6C8], 0
0x18004b6c2  jz      short loc_18004B6D4
0x18004b6c4  lea     rcx, [rsp+720h+var_6E8]
0x18004b6c9  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18004b6ce  jmp     short loc_18004B6D4
0x18004b6d0  mov     byte ptr [rdi+20h], 0
0x18004b6d4  mov     rax, rdi
0x18004b6d7  mov     rcx, [rbp+620h+var_10]
0x18004b6de  xor     rcx, rsp; StackCookie
0x18004b6e1  call    __security_check_cookie
0x18004b6e6  lea     r11, [rsp+720h+var_s0]
0x18004b6ee  mov     rbx, [r11+18h]
0x18004b6f2  mov     rdi, [r11+20h]
0x18004b6f6  mov     rsp, r11
0x18004b6f9  pop     rbp
0x18004b6fa  retn
0x18004b6fb  mov     edx, eax; __int64
0x18004b6fd  mov     [rsp+720h+var_6F8], 1D7h
0x18004b705  lea     rax, aCreateRandomFi; "create_random_file_path"
0x18004b70c  mov     [rsp+720h+var_700], rax
0x18004b711  lea     r9, aSDFailed; "[%s:%d] failed; "
0x18004b718  xor     r8d, r8d; void *
0x18004b71b  lea     rcx, [rbp+620h+pExceptionObject]; this
0x18004b71f  call    ??0system_exception@windiag@@QEAA@_JPEBXPEBDZZ; windiag::system_exception::system_exception(__int64,void const *,char const *,...)
0x18004b724  lea     rdx, _TI2?AUsystem_exception@windiag@@; pThrowInfo
0x18004b72b  lea     rcx, [rbp+620h+pExceptionObject]; pExceptionObject
0x18004b72f  call    _CxxThrowException_0
```
