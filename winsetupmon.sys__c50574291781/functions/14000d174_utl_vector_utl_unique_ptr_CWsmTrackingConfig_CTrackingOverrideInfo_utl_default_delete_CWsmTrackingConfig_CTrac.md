# utl::vector<utl::unique_ptr<CWsmTrackingConfig::CTrackingOverrideInfo,utl::default_delete<CWsmTrackingConfig::CTrackingOverrideInfo>>,utl::allocator<utl::unique_ptr<CWsmTrackingConfig::CTrackingOverrideInfo,utl::default_delete<CWsmTrackingConfig::CTrackingOverrideInfo>>>>::resize(unsigned __int64)

- ea: `0x14000d174`
- end: `0x14000d214`
- name: `?resize@?$vector@V?$unique_ptr@VCTrackingOverrideInfo@CWsmTrackingConfig@@U?$default_delete@VCTrackingOverrideInfo@CWsmTrackingConfig@@@utl@@@utl@@V?$allocator@V?$unique_ptr@VCTrackingOverrideInfo@CWsmTrackingConfig@@U?$default_delete@VCTrackingOverrideInfo@CWsmTrackingConfig@@@utl@@@utl@@@2@@utl@@QEAA_N_K@Z`
- size: `160`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x140009b70`
- `0x14000adb8`
- `0x14000cad0`

## callees

- `0x14000888c`
- `0x14000c0c0`
- `0x14000d174`

## pseudocode

```c
char __fastcall utl::vector<utl::unique_ptr<CWsmTrackingConfig::CTrackingOverrideInfo,utl::default_delete<CWsmTrackingConfig::CTrackingOverrideInfo>>,utl::allocator<utl::unique_ptr<CWsmTrackingConfig::CTrackingOverrideInfo,utl::default_delete<CWsmTrackingConfig::CTrackingOverrideInfo>>>>::resize(
        __int64 *a1,
        unsigned __int64 a2)
{
  __int64 v2; // r8
  __int64 v4; // rcx
  unsigned __int64 v6; // rbp
  __int64 v7; // rdx
  char v8; // bl
  __int64 v9; // rdx
  __int64 v10; // rax
  unsigned __int64 v11; // rcx

  v2 = a1[1];
  v4 = *a1;
  v6 = (v2 - v4) >> 3;
  if ( a2 > v6 )
  {
    if ( a2 <= (a1[2] - v4) >> 3
      || (unsigned __int8)utl::vector<utl::unique_ptr<CWsmTrackingConfig::CTrackingOverrideInfo,utl::default_delete<CWsmTrackingConfig::CTrackingOverrideInfo>>,utl::allocator<utl::unique_ptr<CWsmTrackingConfig::CTrackingOverrideInfo,utl::default_delete<CWsmTrackingConfig::CTrackingOverrideInfo>>>>::_GrowMinimum(a1) )
    {
      v9 = a1[1];
      v10 = 0;
      v8 = 1;
      v11 = a2 - v6;
      if ( a2 != v6 )
      {
        do
          *(_QWORD *)(v9 + 8 * v10++) = 0;
        while ( v10 != v11 );
      }
      utl::_RangeDestroyApc<utl::allocator<utl::unique_ptr<CWsmTrackingConfig::CTrackingOverrideInfo,utl::default_delete<CWsmTrackingConfig::CTrackingOverrideInfo>>>>(
        v11,
        v9,
        0);
      a1[1] = *a1 + 8 * a2;
    }
    else
    {
      return 0;
    }
  }
  else
  {
    v7 = v4 + 8 * a2;
    a1[1] = v7;
    utl::_RangeDestroyApc<utl::allocator<utl::unique_ptr<CWsmTrackingConfig::CTrackingOverrideInfo,utl::default_delete<CWsmTrackingConfig::CTrackingOverrideInfo>>>>(
      v4,
      v7,
      (v2 - v7) >> 3);
    return 1;
  }
  return v8;
}

```

## disassembly

```asm
0x14000d174  push    rbx
0x14000d176  push    rbp
0x14000d177  push    rsi
0x14000d178  push    rdi
0x14000d179  sub     rsp, 28h
0x14000d17d  mov     r8, [rcx+8]
0x14000d181  mov     rdi, rcx
0x14000d184  mov     rcx, [rcx]
0x14000d187  mov     rbp, r8
0x14000d18a  sub     rbp, rcx
0x14000d18d  mov     rsi, rdx
0x14000d190  sar     rbp, 3
0x14000d194  cmp     rdx, rbp
0x14000d197  ja      short loc_14000D1B4
0x14000d199  lea     rdx, [rcx+rdx*8]
0x14000d19d  sub     r8, rdx
0x14000d1a0  mov     [rdi+8], rdx
0x14000d1a4  sar     r8, 3
0x14000d1a8  call    ??$_RangeDestroyApc@V?$allocator@V?$unique_ptr@VCTrackingOverrideInfo@CWsmTrackingConfig@@U?$default_delete@VCTrackingOverrideInfo@CWsmTrackingConfig@@@utl@@@utl@@@utl@@@utl@@YAXAEAV?$allocator@V?$unique_ptr@VCTrackingOverrideInfo@CWsmTrackingConfig@@U?$default_delete@VCTrackingOverrideInfo@CWsmTrackingConfig@@@utl@@@utl@@@0@PEAV?$unique_ptr@VCTrackingOverrideInfo@CWsmTrackingConfig@@U?$default_delete@VCTrackingOverrideInfo@CWsmTrackingConfig@@@utl@@@0@_K@Z; utl::_RangeDestroyApc<utl::allocator<utl::unique_ptr<CWsmTrackingConfig::CTrackingOverrideInfo,utl::default_delete<CWsmTrackingConfig::CTrackingOverrideInfo>>>>(utl::allocator<utl::unique_ptr<CWsmTrackingConfig::CTrackingOverrideInfo,utl::default_delete<CWsmTrackingConfig::CTrackingOverrideInfo>>> &,utl::unique_ptr<CWsmTrackingConfig::CTrackingOverrideInfo,utl::default_delete<CWsmTrackingConfig::CTrackingOverrideInfo>> *,unsigned __int64)
0x14000d1ad  mov     ebx, 1
0x14000d1b2  jmp     short loc_14000D208
0x14000d1b4  mov     rax, [rdi+10h]
0x14000d1b8  sub     rax, rcx
0x14000d1bb  sar     rax, 3
0x14000d1bf  cmp     rsi, rax
0x14000d1c2  jbe     short loc_14000D1D4
0x14000d1c4  mov     rcx, rdi
0x14000d1c7  call    ?_GrowMinimum@?$vector@V?$unique_ptr@VCTrackingOverrideInfo@CWsmTrackingConfig@@U?$default_delete@VCTrackingOverrideInfo@CWsmTrackingConfig@@@utl@@@utl@@V?$allocator@V?$unique_ptr@VCTrackingOverrideInfo@CWsmTrackingConfig@@U?$default_delete@VCTrackingOverrideInfo@CWsmTrackingConfig@@@utl@@@utl@@@2@@utl@@AEAA_N_K@Z; utl::vector<utl::unique_ptr<CWsmTrackingConfig::CTrackingOverrideInfo,utl::default_delete<CWsmTrackingConfig::CTrackingOverrideInfo>>,utl::allocator<utl::unique_ptr<CWsmTrackingConfig::CTrackingOverrideInfo,utl::default_delete<CWsmTrackingConfig::CTrackingOverrideInfo>>>>::_GrowMinimum(unsigned __int64)
0x14000d1cc  test    al, al
0x14000d1ce  jnz     short loc_14000D1D4
0x14000d1d0  xor     bl, bl
0x14000d1d2  jmp     short loc_14000D208
0x14000d1d4  mov     rdx, [rdi+8]
0x14000d1d8  xor     eax, eax
0x14000d1da  mov     rcx, rsi
0x14000d1dd  lea     ebx, [rax+1]
0x14000d1e0  sub     rcx, rbp
0x14000d1e3  jz      short loc_14000D1F5
0x14000d1e5  mov     qword ptr [rdx+rax*8], 0
0x14000d1ed  add     rax, rbx
0x14000d1f0  cmp     rax, rcx
0x14000d1f3  jnz     short loc_14000D1E5
0x14000d1f5  xor     r8d, r8d
0x14000d1f8  call    ??$_RangeDestroyApc@V?$allocator@V?$unique_ptr@VCTrackingOverrideInfo@CWsmTrackingConfig@@U?$default_delete@VCTrackingOverrideInfo@CWsmTrackingConfig@@@utl@@@utl@@@utl@@@utl@@YAXAEAV?$allocator@V?$unique_ptr@VCTrackingOverrideInfo@CWsmTrackingConfig@@U?$default_delete@VCTrackingOverrideInfo@CWsmTrackingConfig@@@utl@@@utl@@@0@PEAV?$unique_ptr@VCTrackingOverrideInfo@CWsmTrackingConfig@@U?$default_delete@VCTrackingOverrideInfo@CWsmTrackingConfig@@@utl@@@0@_K@Z; utl::_RangeDestroyApc<utl::allocator<utl::unique_ptr<CWsmTrackingConfig::CTrackingOverrideInfo,utl::default_delete<CWsmTrackingConfig::CTrackingOverrideInfo>>>>(utl::allocator<utl::unique_ptr<CWsmTrackingConfig::CTrackingOverrideInfo,utl::default_delete<CWsmTrackingConfig::CTrackingOverrideInfo>>> &,utl::unique_ptr<CWsmTrackingConfig::CTrackingOverrideInfo,utl::default_delete<CWsmTrackingConfig::CTrackingOverrideInfo>> *,unsigned __int64)
0x14000d1fd  mov     rcx, [rdi]
0x14000d200  lea     rdx, [rcx+rsi*8]
0x14000d204  mov     [rdi+8], rdx
0x14000d208  mov     al, bl
0x14000d20a  add     rsp, 28h
0x14000d20e  pop     rdi
0x14000d20f  pop     rsi
0x14000d210  pop     rbp
0x14000d211  pop     rbx
0x14000d212  retn
```
