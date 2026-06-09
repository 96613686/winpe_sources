# CSpCfgInstOffline::GetNGramContextCount(ulong *)

- ea: `0x18005dcac`
- end: `0x18005dd8d`
- name: `?GetNGramContextCount@CSpCfgInstOffline@@AEAAJPEAK@Z`
- size: `225`
- prototype: `__int64 __fastcall(CSpCfgInstOffline *__hidden this, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x18005e5e8`

## callees

- `0x1800034b0`
- `0x18005dcac`
- `0x1800d4920`
- `0x1800d4a2c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005dd5d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005dd5d`

## pseudocode

```c
__int64 __fastcall CSpCfgInstOffline::GetNGramContextCount(CSpCfgInstOffline *this, unsigned int *a2)
{
  unsigned int v2; // esi
  unsigned int v3; // edi
  CSpCfgData *v6; // rcx
  unsigned int v7; // r9d
  int NGramRuleByIndex; // ebx
  __int128 v10; // [rsp+20h] [rbp-348h] BYREF
  __int128 v11; // [rsp+30h] [rbp-338h]
  _BYTE v12[48]; // [rsp+40h] [rbp-328h] BYREF
  int v13; // [rsp+70h] [rbp-2F8h]
  LPVOID pv[2]; // [rsp+B0h] [rbp-2B8h]

  v2 = 0;
  *a2 = 0;
  v3 = 0;
  *(_OWORD *)pv = 0;
  while ( v3 < *((_DWORD *)this + 26) )
  {
    v6 = (CSpCfgData *)*((_QWORD *)this + 32);
    v10 = 0;
    v11 = 0;
    CSpCfgData::GetRuleDataByIndex(v6, v3, (struct SPRULEDATA *)&v10);
    if ( !BYTE3(v10) && BYTE8(v11) )
    {
      NGramRuleByIndex = CSpCfgData::GetNGramRuleByIndex(
                           *((CSpCfgData **)this + 32),
                           v3,
                           (struct CSpNGramRule *)v12,
                           v7);
      if ( NGramRuleByIndex < 0 )
        goto LABEL_11;
      if ( !v13 )
      {
        NGramRuleByIndex = -2147024809;
        goto LABEL_11;
      }
      v2 += v13;
    }
    ++v3;
  }
  *a2 = v2;
  NGramRuleByIndex = 0;
LABEL_11:
  CoTaskMemFree(pv[1]);
  return (unsigned int)NGramRuleByIndex;
}

```

## disassembly

```asm
0x18005dcac  mov     [rsp+arg_10], rbx
0x18005dcb1  mov     [rsp+arg_18], rbp
0x18005dcb6  push    rsi
0x18005dcb7  push    rdi
0x18005dcb8  push    r14
0x18005dcba  sub     rsp, 350h
0x18005dcc1  mov     rax, cs:__security_cookie
0x18005dcc8  xor     rax, rsp
0x18005dccb  mov     [rsp+368h+var_28], rax
0x18005dcd3  xor     esi, esi
0x18005dcd5  mov     dword ptr [rdx], 0
0x18005dcdb  xorps   xmm0, xmm0
0x18005dcde  xor     edi, edi
0x18005dce0  movdqa  xmmword ptr [rsp+368h+pv], xmm0
0x18005dce9  mov     r14, rdx
0x18005dcec  mov     rbp, rcx
0x18005dcef  cmp     edi, [rbp+68h]
0x18005dcf2  jnb     short loc_18005DD50
0x18005dcf4  mov     rcx, [rbp+100h]; this
0x18005dcfb  lea     r8, [rsp+368h+var_348]; struct SPRULEDATA *
0x18005dd00  xorps   xmm0, xmm0
0x18005dd03  mov     edx, edi; unsigned int
0x18005dd05  movups  [rsp+368h+var_348], xmm0
0x18005dd0a  movups  [rsp+368h+var_338], xmm0
0x18005dd0f  call    ?GetRuleDataByIndex@CSpCfgData@@QEAAXKPEAUSPRULEDATA@@@Z; CSpCfgData::GetRuleDataByIndex(ulong,SPRULEDATA *)
0x18005dd14  cmp     byte ptr [rsp+368h+var_348+3], 0
0x18005dd19  jnz     short loc_18005DD45
0x18005dd1b  cmp     byte ptr [rsp+368h+var_338+8], 0
0x18005dd20  jz      short loc_18005DD45
0x18005dd22  mov     rcx, [rbp+100h]; this
0x18005dd29  lea     r8, [rsp+368h+var_328]; struct CSpNGramRule *
0x18005dd2e  mov     edx, edi; unsigned int
0x18005dd30  call    ?GetNGramRuleByIndex@CSpCfgData@@QEAAJKPEAVCSpNGramRule@@K@Z; CSpCfgData::GetNGramRuleByIndex(ulong,CSpNGramRule *,ulong)
0x18005dd35  mov     ebx, eax
0x18005dd37  test    eax, eax
0x18005dd39  js      short loc_18005DD55
0x18005dd3b  mov     eax, [rsp+368h+var_2F8]
0x18005dd3f  test    eax, eax
0x18005dd41  jz      short loc_18005DD49
0x18005dd43  add     esi, eax
0x18005dd45  inc     edi
0x18005dd47  jmp     short loc_18005DCEF
0x18005dd49  mov     ebx, 80070057h
0x18005dd4e  jmp     short loc_18005DD55
0x18005dd50  mov     [r14], esi
0x18005dd53  xor     ebx, ebx
0x18005dd55  mov     rcx, [rsp+368h+pv+8]; pv
0x18005dd5d  call    cs:__imp_CoTaskMemFree
0x18005dd63  mov     eax, ebx
0x18005dd65  mov     rcx, [rsp+368h+var_28]
0x18005dd6d  xor     rcx, rsp; StackCookie
0x18005dd70  call    __security_check_cookie
0x18005dd75  lea     r11, [rsp+368h+var_18]
0x18005dd7d  mov     rbx, [r11+30h]
0x18005dd81  mov     rbp, [r11+38h]
0x18005dd85  mov     rsp, r11
0x18005dd88  pop     r14
0x18005dd8a  pop     rdi
0x18005dd8b  pop     rsi
0x18005dd8c  retn
```
