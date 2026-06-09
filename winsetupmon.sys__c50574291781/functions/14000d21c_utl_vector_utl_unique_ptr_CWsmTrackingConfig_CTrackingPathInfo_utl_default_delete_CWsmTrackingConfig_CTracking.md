# utl::vector<utl::unique_ptr<CWsmTrackingConfig::CTrackingPathInfo,utl::default_delete<CWsmTrackingConfig::CTrackingPathInfo>>,utl::allocator<utl::unique_ptr<CWsmTrackingConfig::CTrackingPathInfo,utl::default_delete<CWsmTrackingConfig::CTrackingPathInfo>>>>::resize(unsigned __int64)

- ea: `0x14000d21c`
- end: `0x14000d2ed`
- name: `?resize@?$vector@V?$unique_ptr@VCTrackingPathInfo@CWsmTrackingConfig@@U?$default_delete@VCTrackingPathInfo@CWsmTrackingConfig@@@utl@@@utl@@V?$allocator@V?$unique_ptr@VCTrackingPathInfo@CWsmTrackingConfig@@U?$default_delete@VCTrackingPathInfo@CWsmTrackingConfig@@@utl@@@utl@@@2@@utl@@QEAA_N_K@Z`
- size: `209`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x14000960c`
- `0x14000a0fc`
- `0x14000ab4c`
- `0x14000c6f0`

## callees

- `0x1400088ec`
- `0x14000c1d8`
- `0x14000d21c`

## pseudocode

```c
char __fastcall utl::vector<utl::unique_ptr<CWsmTrackingConfig::CTrackingPathInfo,utl::default_delete<CWsmTrackingConfig::CTrackingPathInfo>>,utl::allocator<utl::unique_ptr<CWsmTrackingConfig::CTrackingPathInfo,utl::default_delete<CWsmTrackingConfig::CTrackingPathInfo>>>>::resize(
        __int64 *a1,
        unsigned __int64 a2)
{
  __int64 v2; // rax
  __int64 v4; // rdx
  unsigned __int64 v6; // rbp
  __int64 v7; // rdx
  char v8; // di
  unsigned __int64 v9; // rcx
  unsigned __int64 v10; // rdx
  __int64 v11; // rcx

  v2 = a1[1];
  v4 = *a1;
  v6 = (v2 - *a1) >> 3;
  if ( a2 > v6 )
  {
    v9 = (a1[2] - v4) >> 3;
    if ( a2 > v9 )
    {
      v10 = 7 * (v9 >> 2) + 8;
      if ( v10 < a2 )
        v10 = a2;
      if ( v10 > 0xFFFFFFFFFFFFFFFLL )
        v10 = 0xFFFFFFFFFFFFFFFLL;
      if ( a2 > v10
        || !(unsigned __int8)utl::vector<utl::unique_ptr<CWsmTrackingConfig::CTrackingPathInfo,utl::default_delete<CWsmTrackingConfig::CTrackingPathInfo>>,utl::allocator<utl::unique_ptr<CWsmTrackingConfig::CTrackingPathInfo,utl::default_delete<CWsmTrackingConfig::CTrackingPathInfo>>>>::_SetCapacity(a1) )
      {
        return 0;
      }
      v2 = a1[1];
    }
    v11 = 0;
    v8 = 1;
    if ( a2 != v6 )
    {
      do
        *(_QWORD *)(v2 + 8 * v11++) = 0;
      while ( v11 != a2 - v6 );
    }
    utl::_RangeDestroyApc<utl::allocator<utl::unique_ptr<CWsmTrackingConfig::CTrackingPathInfo,utl::default_delete<CWsmTrackingConfig::CTrackingPathInfo>>>>(
      v11,
      v2,
      0);
    a1[1] = *a1 + 8 * a2;
  }
  else
  {
    v7 = v4 + 8 * a2;
    a1[1] = v7;
    utl::_RangeDestroyApc<utl::allocator<utl::unique_ptr<CWsmTrackingConfig::CTrackingPathInfo,utl::default_delete<CWsmTrackingConfig::CTrackingPathInfo>>>>(
      (__int64)a1,
      v7,
      (v2 - v7) >> 3);
    return 1;
  }
  return v8;
}

```

## disassembly

```asm
0x14000d21c  push    rbx
0x14000d21e  push    rbp
0x14000d21f  push    rsi
0x14000d220  push    rdi
0x14000d221  sub     rsp, 28h
0x14000d225  mov     rax, [rcx+8]
0x14000d229  mov     rsi, rdx
0x14000d22c  mov     rdx, [rcx]
0x14000d22f  mov     rbp, rax
0x14000d232  sub     rbp, rdx
0x14000d235  mov     rbx, rcx
0x14000d238  sar     rbp, 3
0x14000d23c  cmp     rsi, rbp
0x14000d23f  ja      short loc_14000D25F
0x14000d241  lea     rdx, [rdx+rsi*8]
0x14000d245  sub     rax, rdx
0x14000d248  mov     [rcx+8], rdx
0x14000d24c  sar     rax, 3
0x14000d250  mov     r8, rax
0x14000d253  call    ??$_RangeDestroyApc@V?$allocator@V?$unique_ptr@VCTrackingPathInfo@CWsmTrackingConfig@@U?$default_delete@VCTrackingPathInfo@CWsmTrackingConfig@@@utl@@@utl@@@utl@@@utl@@YAXAEAV?$allocator@V?$unique_ptr@VCTrackingPathInfo@CWsmTrackingConfig@@U?$default_delete@VCTrackingPathInfo@CWsmTrackingConfig@@@utl@@@utl@@@0@PEAV?$unique_ptr@VCTrackingPathInfo@CWsmTrackingConfig@@U?$default_delete@VCTrackingPathInfo@CWsmTrackingConfig@@@utl@@@0@_K@Z; utl::_RangeDestroyApc<utl::allocator<utl::unique_ptr<CWsmTrackingConfig::CTrackingPathInfo,utl::default_delete<CWsmTrackingConfig::CTrackingPathInfo>>>>(utl::allocator<utl::unique_ptr<CWsmTrackingConfig::CTrackingPathInfo,utl::default_delete<CWsmTrackingConfig::CTrackingPathInfo>>> &,utl::unique_ptr<CWsmTrackingConfig::CTrackingPathInfo,utl::default_delete<CWsmTrackingConfig::CTrackingPathInfo>> *,unsigned __int64)
0x14000d258  mov     edi, 1
0x14000d25d  jmp     short loc_14000D2DB
0x14000d25f  mov     rcx, [rcx+10h]
0x14000d263  sub     rcx, rdx
0x14000d266  sar     rcx, 3
0x14000d26a  cmp     rsi, rcx
0x14000d26d  jbe     short loc_14000D2A8
0x14000d26f  shr     rcx, 2
0x14000d273  mov     rax, 0FFFFFFFFFFFFFFFh
0x14000d27d  imul    rdx, rcx, 7
0x14000d281  add     rdx, 8
0x14000d285  cmp     rdx, rsi
0x14000d288  cmovb   rdx, rsi
0x14000d28c  cmp     rdx, rax
0x14000d28f  cmova   rdx, rax
0x14000d293  cmp     rsi, rdx
0x14000d296  ja      short loc_14000D2E8
0x14000d298  mov     rcx, rbx
0x14000d29b  call    ?_SetCapacity@?$vector@V?$unique_ptr@VCTrackingPathInfo@CWsmTrackingConfig@@U?$default_delete@VCTrackingPathInfo@CWsmTrackingConfig@@@utl@@@utl@@V?$allocator@V?$unique_ptr@VCTrackingPathInfo@CWsmTrackingConfig@@U?$default_delete@VCTrackingPathInfo@CWsmTrackingConfig@@@utl@@@utl@@@2@@utl@@AEAA_N_K@Z; utl::vector<utl::unique_ptr<CWsmTrackingConfig::CTrackingPathInfo,utl::default_delete<CWsmTrackingConfig::CTrackingPathInfo>>,utl::allocator<utl::unique_ptr<CWsmTrackingConfig::CTrackingPathInfo,utl::default_delete<CWsmTrackingConfig::CTrackingPathInfo>>>>::_SetCapacity(unsigned __int64)
0x14000d2a0  test    al, al
0x14000d2a2  jz      short loc_14000D2E8
0x14000d2a4  mov     rax, [rbx+8]
0x14000d2a8  xor     ecx, ecx
0x14000d2aa  mov     rdx, rsi
0x14000d2ad  lea     edi, [rcx+1]
0x14000d2b0  sub     rdx, rbp
0x14000d2b3  jz      short loc_14000D2C5
0x14000d2b5  mov     qword ptr [rax+rcx*8], 0
0x14000d2bd  add     rcx, rdi
0x14000d2c0  cmp     rcx, rdx
0x14000d2c3  jnz     short loc_14000D2B5
0x14000d2c5  xor     r8d, r8d
0x14000d2c8  mov     rdx, rax
0x14000d2cb  call    ??$_RangeDestroyApc@V?$allocator@V?$unique_ptr@VCTrackingPathInfo@CWsmTrackingConfig@@U?$default_delete@VCTrackingPathInfo@CWsmTrackingConfig@@@utl@@@utl@@@utl@@@utl@@YAXAEAV?$allocator@V?$unique_ptr@VCTrackingPathInfo@CWsmTrackingConfig@@U?$default_delete@VCTrackingPathInfo@CWsmTrackingConfig@@@utl@@@utl@@@0@PEAV?$unique_ptr@VCTrackingPathInfo@CWsmTrackingConfig@@U?$default_delete@VCTrackingPathInfo@CWsmTrackingConfig@@@utl@@@0@_K@Z; utl::_RangeDestroyApc<utl::allocator<utl::unique_ptr<CWsmTrackingConfig::CTrackingPathInfo,utl::default_delete<CWsmTrackingConfig::CTrackingPathInfo>>>>(utl::allocator<utl::unique_ptr<CWsmTrackingConfig::CTrackingPathInfo,utl::default_delete<CWsmTrackingConfig::CTrackingPathInfo>>> &,utl::unique_ptr<CWsmTrackingConfig::CTrackingPathInfo,utl::default_delete<CWsmTrackingConfig::CTrackingPathInfo>> *,unsigned __int64)
0x14000d2d0  mov     rcx, [rbx]
0x14000d2d3  lea     rdx, [rcx+rsi*8]
0x14000d2d7  mov     [rbx+8], rdx
0x14000d2db  mov     al, dil
0x14000d2de  add     rsp, 28h
0x14000d2e2  pop     rdi
0x14000d2e3  pop     rsi
0x14000d2e4  pop     rbp
0x14000d2e5  pop     rbx
0x14000d2e6  retn
0x14000d2e8  xor     dil, dil
0x14000d2eb  jmp     short loc_14000D2DB
```
