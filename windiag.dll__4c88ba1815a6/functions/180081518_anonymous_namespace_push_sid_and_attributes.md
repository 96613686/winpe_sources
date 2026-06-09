# _anonymous_namespace_::push_sid_and_attributes

- ea: `0x180081518`
- end: `0x18008165a`
- name: `_anonymous_namespace_::push_sid_and_attributes`
- size: `322`
- prototype: `__int64 __fastcall(struct lua_State *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800833b0`

## callees

- `0x180006c50`
- `0x180006d40`
- `0x180007160`
- `0x18003b0bc`
- `0x180081518`
- `0x180083790`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180081573`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180081573`
- `api-ms-win-security-sddl-ansi-l1-1-0!ConvertSidToStringSidA` at `0x18008154d`
- `api-ms-win-security-sddl-ansi-l1-1-0!ConvertSidToStringSidA` at `0x18008154d`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall anonymous_namespace_::push_sid_and_attributes(struct lua_State *a1, __int64 a2)
{
  void *v4; // rcx
  LPSTR v5; // rbx
  char v6; // al
  const char *v7; // rdx
  const char *v8; // rdx
  char *v9[4]; // [rsp+20h] [rbp-50h] BYREF
  char *v10[4]; // [rsp+40h] [rbp-30h] BYREF
  int v11; // [rsp+60h] [rbp-10h]
  __int64 v12; // [rsp+68h] [rbp-8h]
  LPSTR StringSid; // [rsp+98h] [rbp+28h] BYREF
  LPSTR v14; // [rsp+A0h] [rbp+30h]

  v4 = *(void **)a2;
  StringSid = 0;
  if ( v4 && ConvertSidToStringSidA(v4, &StringSid) )
  {
    v5 = StringSid;
    v14 = StringSid;
    lua_pushstring(a1, StringSid);
    if ( v5 )
      LocalFree(v5);
    lua_setfield(a1, 4294967294LL, "sid");
  }
  lua_pushinteger(a1, *(unsigned int *)(a2 + 8));
  lua_setfield(a1, 4294967294LL, "attributes");
  anonymous_namespace_::sid_account_name((__int64)v9, *(void **)a2);
  v6 = v12;
  if ( (_BYTE)v12 )
  {
    v7 = (const char *)v9;
    if ( v9[3] > (char *)0xF )
      v7 = v9[0];
    lua_pushstring(a1, v7);
    lua_setfield(a1, 4294967294LL, "name");
    v8 = (const char *)v10;
    if ( v10[3] > (char *)0xF )
      v8 = v10[0];
    lua_pushstring(a1, v8);
    lua_setfield(a1, 4294967294LL, "domain");
    lua_pushinteger(a1, v11);
    lua_setfield(a1, 4294967294LL, "snu");
    v6 = v12;
  }
  if ( v6 )
  {
    std::string::~string(v10);
    std::string::~string(v9);
  }
}

```

## disassembly

```asm
0x180081518  mov     [rsp-18h+arg_0], rbx
0x18008151d  mov     [rsp-18h+arg_18], rsi
0x180081522  push    rbp
0x180081523  push    rdi
0x180081524  push    r14
0x180081526  mov     rbp, rsp
0x180081529  sub     rsp, 70h
0x18008152d  mov     rsi, rdx
0x180081530  mov     rdi, rcx
0x180081533  mov     rcx, [rdx]; Sid
0x180081536  mov     [rbp+StringSid], 0
0x18008153e  mov     r14d, 0FFFFFFFEh
0x180081544  test    rcx, rcx
0x180081547  jz      short loc_18008158B
0x180081549  lea     rdx, [rbp+StringSid]; StringSid
0x18008154d  call    cs:__imp_ConvertSidToStringSidA
0x180081553  test    eax, eax
0x180081555  jz      short loc_18008158B
0x180081557  mov     rbx, [rbp+StringSid]
0x18008155b  mov     [rbp+arg_10], rbx
0x18008155f  mov     rdx, rbx; char *
0x180081562  mov     rcx, rdi; struct lua_State *
0x180081565  call    ?lua_pushstring@@YAPEBDPEAUlua_State@@PEBD@Z; lua_pushstring(lua_State *,char const *)
0x18008156a  nop
0x18008156b  test    rbx, rbx
0x18008156e  jz      short loc_180081579
0x180081570  mov     rcx, rbx; hMem
0x180081573  call    cs:__imp_LocalFree
0x180081579  lea     r8, aSid; "sid"
0x180081580  mov     edx, r14d; int
0x180081583  mov     rcx, rdi; struct lua_State *
0x180081586  call    ?lua_setfield@@YAXPEAUlua_State@@HPEBD@Z; lua_setfield(lua_State *,int,char const *)
0x18008158b  mov     edx, [rsi+8]; __int64
0x18008158e  mov     rcx, rdi; struct lua_State *
0x180081591  call    ?lua_pushinteger@@YAXPEAUlua_State@@_J@Z; lua_pushinteger(lua_State *,__int64)
0x180081596  lea     r8, aAttributes; "attributes"
0x18008159d  mov     edx, r14d; int
0x1800815a0  mov     rcx, rdi; struct lua_State *
0x1800815a3  call    ?lua_setfield@@YAXPEAUlua_State@@HPEBD@Z; lua_setfield(lua_State *,int,char const *)
0x1800815a8  mov     rdx, [rsi]
0x1800815ab  lea     rcx, [rbp+var_50]
0x1800815af  call    _anonymous_namespace___sid_account_name
0x1800815b4  nop
0x1800815b5  mov     rax, [rbp+var_8]
0x1800815b9  test    al, al
0x1800815bb  jz      short loc_18008162F
0x1800815bd  lea     rdx, [rbp+var_50]
0x1800815c1  cmp     [rbp+var_38], 0Fh
0x1800815c6  cmova   rdx, [rbp+var_50]; char *
0x1800815cb  mov     rcx, rdi; struct lua_State *
0x1800815ce  call    ?lua_pushstring@@YAPEBDPEAUlua_State@@PEBD@Z; lua_pushstring(lua_State *,char const *)
0x1800815d3  lea     r8, aName; "name"
0x1800815da  mov     edx, r14d; int
0x1800815dd  mov     rcx, rdi; struct lua_State *
0x1800815e0  call    ?lua_setfield@@YAXPEAUlua_State@@HPEBD@Z; lua_setfield(lua_State *,int,char const *)
0x1800815e5  lea     rdx, [rbp+var_30]
0x1800815e9  cmp     [rbp+var_18], 0Fh
0x1800815ee  cmova   rdx, [rbp+var_30]; char *
0x1800815f3  mov     rcx, rdi; struct lua_State *
0x1800815f6  call    ?lua_pushstring@@YAPEBDPEAUlua_State@@PEBD@Z; lua_pushstring(lua_State *,char const *)
0x1800815fb  lea     r8, aDomain; "domain"
0x180081602  mov     edx, r14d; int
0x180081605  mov     rcx, rdi; struct lua_State *
0x180081608  call    ?lua_setfield@@YAXPEAUlua_State@@HPEBD@Z; lua_setfield(lua_State *,int,char const *)
0x18008160d  movsxd  rdx, [rbp+var_10]; __int64
0x180081611  mov     rcx, rdi; struct lua_State *
0x180081614  call    ?lua_pushinteger@@YAXPEAUlua_State@@_J@Z; lua_pushinteger(lua_State *,__int64)
0x180081619  lea     r8, aSnu; "snu"
0x180081620  mov     edx, r14d; int
0x180081623  mov     rcx, rdi; struct lua_State *
0x180081626  call    ?lua_setfield@@YAXPEAUlua_State@@HPEBD@Z; lua_setfield(lua_State *,int,char const *)
0x18008162b  mov     rax, [rbp+var_8]
0x18008162f  test    al, al
0x180081631  jz      short loc_180081645
0x180081633  lea     rcx, [rbp+var_30]
0x180081637  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18008163c  lea     rcx, [rbp+var_50]
0x180081640  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180081645  lea     r11, [rsp+70h+var_s0]
0x18008164a  mov     rbx, [r11+20h]
0x18008164e  mov     rsi, [r11+38h]
0x180081652  mov     rsp, r11
0x180081655  pop     r14
0x180081657  pop     rdi
0x180081658  pop     rbp
0x180081659  retn
```
