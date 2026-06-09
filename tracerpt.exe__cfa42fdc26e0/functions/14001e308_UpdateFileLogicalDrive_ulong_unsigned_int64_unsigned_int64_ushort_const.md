# UpdateFileLogicalDrive(ulong,unsigned __int64,unsigned __int64,ushort const *)

- ea: `0x14001e308`
- end: `0x14001e3c1`
- name: `?UpdateFileLogicalDrive@@YAXK_K0PEBG@Z`
- size: `185`
- prototype: `void __fastcall(int, __int64, __int64, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x140006db8`

## callees

- `0x14001b10c`
- `0x14001e308`

## import_xrefs

- `ntdll!RtlEnterCriticalSection` at `0x14001e33e`
- `ntdll!RtlEnterCriticalSection` at `0x14001e33e`
- `ntdll!RtlLeaveCriticalSection` at `0x14001e3b3`
- `ntdll!RtlLeaveCriticalSection` at `0x14001e3b3`

## pseudocode

```c
void __fastcall UpdateFileLogicalDrive(int a1, __int64 a2, __int64 a3, const unsigned __int16 *a4)
{
  __int64 v4; // rax
  _QWORD *v5; // rdi
  _QWORD *v6; // rbx
  _QWORD *i; // rbx
  __int64 v8; // [rsp+20h] [rbp-30h] BYREF
  _QWORD v9[5]; // [rsp+28h] [rbp-28h] BYREF
  int v10; // [rsp+70h] [rbp+20h] BYREF
  __int64 v11; // [rsp+78h] [rbp+28h] BYREF
  __int64 v12; // [rsp+80h] [rbp+30h] BYREF
  const unsigned __int16 *v13; // [rsp+88h] [rbp+38h] BYREF

  v13 = a4;
  v12 = a3;
  v11 = a2;
  v10 = a1;
  v4 = -1;
  do
    ++v4;
  while ( a4[v4] );
  v8 = v4;
  RtlEnterCriticalSection(&TLCritSect);
  v5 = Block;
  v9[0] = &v10;
  v9[1] = &v11;
  v9[2] = &v12;
  v6 = *(_QWORD **)Block;
  v9[3] = &v8;
  v9[4] = &v13;
  while ( v6 != v5 )
  {
    lambda_1421a5eb1d0382c0cf40c58b0f1a1e45_::operator()(v9, v6 + 4);
    v6 = (_QWORD *)*v6;
  }
  for ( i = qword_140082158; ; lambda_1421a5eb1d0382c0cf40c58b0f1a1e45_::operator()(v9, i + 1) )
  {
    i = (_QWORD *)*i;
    if ( i == (_QWORD *)-1LL )
      break;
  }
  RtlLeaveCriticalSection(&TLCritSect);
}

```

## disassembly

```asm
0x14001e308  mov     rax, rsp
0x14001e30b  mov     [rax+20h], r9
0x14001e30f  mov     [rax+18h], r8
0x14001e313  mov     [rax+10h], rdx
0x14001e317  mov     [rax+8], ecx
0x14001e31a  push    rbp
0x14001e31b  push    rbx
0x14001e31c  push    rdi
0x14001e31d  mov     rbp, rsp
0x14001e320  sub     rsp, 50h
0x14001e324  or      rax, 0FFFFFFFFFFFFFFFFh
0x14001e328  inc     rax
0x14001e32b  cmp     word ptr [r9+rax*2], 0
0x14001e331  jnz     short loc_14001E328
0x14001e333  lea     rcx, ?TLCritSect@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x14001e33a  mov     [rbp+var_30], rax
0x14001e33e  call    cs:__imp_RtlEnterCriticalSection
0x14001e344  mov     rdi, cs:Block
0x14001e34b  lea     rax, [rbp+arg_0]
0x14001e34f  mov     [rbp+var_28], rax
0x14001e353  lea     rax, [rbp+arg_8]
0x14001e357  mov     [rbp+var_20], rax
0x14001e35b  lea     rax, [rbp+arg_10]
0x14001e35f  mov     [rbp+var_18], rax
0x14001e363  lea     rax, [rbp+var_30]
0x14001e367  mov     rbx, [rdi]
0x14001e36a  mov     [rbp+var_10], rax
0x14001e36e  lea     rax, [rbp+arg_18]
0x14001e372  mov     [rbp+var_8], rax
0x14001e376  cmp     rbx, rdi
0x14001e379  jz      short loc_14001E38D
0x14001e37b  lea     rdx, [rbx+20h]
0x14001e37f  lea     rcx, [rbp+var_28]
0x14001e383  call    _lambda_1421a5eb1d0382c0cf40c58b0f1a1e45___operator__
0x14001e388  mov     rbx, [rbx]
0x14001e38b  jmp     short loc_14001E376
0x14001e38d  mov     rbx, cs:qword_140082158
0x14001e394  mov     rbx, [rbx]
0x14001e397  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x14001e39b  jz      short loc_14001E3AC
0x14001e39d  lea     rdx, [rbx+8]
0x14001e3a1  lea     rcx, [rbp+var_28]
0x14001e3a5  call    _lambda_1421a5eb1d0382c0cf40c58b0f1a1e45___operator__
0x14001e3aa  jmp     short loc_14001E394
0x14001e3ac  lea     rcx, ?TLCritSect@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x14001e3b3  call    cs:__imp_RtlLeaveCriticalSection
0x14001e3b9  add     rsp, 50h
0x14001e3bd  pop     rdi
0x14001e3be  pop     rbx
0x14001e3bf  pop     rbp
0x14001e3c0  retn
```
