# DoesAppPoolExist(ushort const *,int *)

- ea: `0x180002e7c`
- end: `0x180002f96`
- name: `?DoesAppPoolExist@@YAJPEBGPEAH@Z`
- size: `282`
- prototype: `__int64 __fastcall(const unsigned __int16 *, int *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180002730`
- `0x180002d30`

## callees

- `0x180002e7c`
- `0x180006822`
- `0x180006850`
- `0x180007010`

## import_xrefs

- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180002ee0`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180002ef4`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180002ee0`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180002ef4`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180002f69`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180002f69`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180002ece`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180002ece`

## pseudocode

```c
__int64 __fastcall DoesAppPoolExist(const unsigned __int16 *a1, int *a2)
{
  int v4; // ebx
  LPVOID v5; // rdi
  int v6; // ebx
  unsigned int v8; // [rsp+40h] [rbp-D8h] BYREF
  _BYTE v9[32]; // [rsp+48h] [rbp-D0h] BYREF
  __int64 v10; // [rsp+68h] [rbp-B0h]
  unsigned __int16 v11[64]; // [rsp+80h] [rbp-98h] BYREF

  memset_0(v11, 0, sizeof(v11));
  STRU::STRU((STRU *)v9, v11, 0x40u);
  v4 = STRU::Append((STRU *)v9, L"/LM/W3SVC/AppPools/");
  if ( v4 >= 0 )
  {
    v4 = STRU::Append((STRU *)v9, a1);
    if ( v4 >= 0 )
    {
      v5 = WamRegMetabaseConfig::m_pMetabase;
      v6 = 1;
      v8 = 0;
      if ( (*(int (__fastcall **)(LPVOID, _QWORD, __int64, __int64, int, unsigned int *))(*(_QWORD *)WamRegMetabaseConfig::m_pMetabase
                                                                                        + 136LL))(
             WamRegMetabaseConfig::m_pMetabase,
             0,
             v10,
             1,
             30000,
             &v8) < 0 )
        v6 = 0;
      else
        (*(void (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)v5 + 144LL))(v5, v8);
      *a2 = v6;
      v4 = 0;
    }
  }
  STRU::~STRU((STRU *)v9);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180002e7c  mov     [rsp+arg_10], rbx
0x180002e81  mov     [rsp+arg_18], rsi
0x180002e86  push    rdi
0x180002e87  sub     rsp, 110h
0x180002e8e  mov     rax, cs:__security_cookie
0x180002e95  xor     rax, rsp
0x180002e98  mov     [rsp+118h+var_18], rax
0x180002ea0  mov     rsi, rdx
0x180002ea3  mov     rdi, rcx
0x180002ea6  xor     edx, edx; Val
0x180002ea8  lea     rcx, [rsp+118h+var_98]; void *
0x180002eb0  mov     r8d, 80h; Size
0x180002eb6  call    memset_0
0x180002ebb  mov     r8d, 40h ; '@'
0x180002ec1  lea     rdx, [rsp+118h+var_98]
0x180002ec9  lea     rcx, [rsp+118h+var_D0]
0x180002ece  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180002ed4  lea     rdx, aLmW3svcApppool; "/LM/W3SVC/AppPools/"
0x180002edb  lea     rcx, [rsp+118h+var_D0]
0x180002ee0  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180002ee6  mov     ebx, eax
0x180002ee8  test    eax, eax
0x180002eea  js      short loc_180002F64
0x180002eec  mov     rdx, rdi
0x180002eef  lea     rcx, [rsp+118h+var_D0]
0x180002ef4  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180002efa  mov     ebx, eax
0x180002efc  test    eax, eax
0x180002efe  js      short loc_180002F64
0x180002f00  mov     rdi, cs:?m_pMetabase@WamRegMetabaseConfig@@0PEAUIMSAdminBaseW@@EA; IMSAdminBaseW * WamRegMetabaseConfig::m_pMetabase
0x180002f07  lea     rcx, [rsp+118h+var_D8]
0x180002f0c  mov     r8, [rsp+118h+var_B0]
0x180002f11  mov     ebx, 1
0x180002f16  mov     [rsp+118h+var_F0], rcx
0x180002f1b  mov     r9d, ebx
0x180002f1e  mov     [rsp+118h+var_D8], 0
0x180002f26  xor     edx, edx
0x180002f28  mov     rax, [rdi]
0x180002f2b  mov     rcx, rdi
0x180002f2e  mov     [rsp+118h+var_F8], 7530h
0x180002f36  mov     rax, [rax+88h]
0x180002f3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f42  test    eax, eax
0x180002f44  js      short loc_180002F5E
0x180002f46  mov     rax, [rdi]
0x180002f49  mov     rcx, rdi
0x180002f4c  mov     edx, [rsp+118h+var_D8]
0x180002f50  mov     rax, [rax+90h]
0x180002f57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f5c  jmp     short loc_180002F60
0x180002f5e  xor     ebx, ebx
0x180002f60  mov     [rsi], ebx
0x180002f62  xor     ebx, ebx
0x180002f64  lea     rcx, [rsp+118h+var_D0]
0x180002f69  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180002f6f  mov     eax, ebx
0x180002f71  mov     rcx, [rsp+118h+var_18]
0x180002f79  xor     rcx, rsp; StackCookie
0x180002f7c  call    __security_check_cookie
0x180002f81  lea     r11, [rsp+118h+var_8]
0x180002f89  mov     rbx, [r11+20h]
0x180002f8d  mov     rsi, [r11+28h]
0x180002f91  mov     rsp, r11
0x180002f94  pop     rdi
0x180002f95  retn
```
