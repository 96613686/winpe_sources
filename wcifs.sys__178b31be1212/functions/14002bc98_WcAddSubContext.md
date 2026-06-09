# WcAddSubContext

- ea: `0x14002bc98`
- end: `0x14002bd68`
- name: `WcAddSubContext`
- size: `208`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x14002ba40`

## callees

- `0x1400020c4`
- `0x1400080c0`
- `0x14002bc98`

## import_xrefs

- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x14002bcb6`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x14002bcb6`

## pseudocode

```c
__int64 __fastcall WcAddSubContext(__int64 a1, __int64 a2, __int64 a3, int a4)
{
  _DWORD *v8; // rax
  int v9; // edx
  _DWORD *v10; // rbx
  _QWORD *v11; // rax
  unsigned int v12; // edi

  v8 = ExAllocateFromPagedLookasideList(&Lookaside);
  v10 = v8;
  if ( v8 )
  {
    memset(v8, 0, 0x50u);
    v10[4] = a4;
    *((_QWORD *)v10 + 4) = a3;
    *((_QWORD *)v10 + 5) = a2;
    v11 = *(_QWORD **)(a1 + 8);
    if ( *v11 != a1 )
      __fastfail(3u);
    *(_QWORD *)v10 = a1;
    v12 = 0;
    *((_QWORD *)v10 + 1) = v11;
    *v11 = v10;
    *(_QWORD *)(a1 + 8) = v10;
  }
  else
  {
    v12 = -1073741670;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v9) = 2;
      WPP_RECORDER_SF_sDd(
        wil_details_featureDescriptors_a->DeviceExtension,
        v9,
        18,
        21,
        (__int64)WPP_c1e0b6795ecc304cffe05d8888ed3789_Traceguids,
        (__int64)"onecore\\base\\fs\\wci\\wcifs\\dir.c",
        111,
        154);
    }
  }
  return v12;
}

```

## disassembly

```asm
0x14002bc98  push    rbx
0x14002bc9a  push    rbp
0x14002bc9b  push    rsi
0x14002bc9c  push    rdi
0x14002bc9d  push    r14
0x14002bc9f  sub     rsp, 40h
0x14002bca3  mov     rsi, rcx
0x14002bca6  mov     edi, r9d
0x14002bca9  lea     rcx, Lookaside; Lookaside
0x14002bcb0  mov     rbp, r8
0x14002bcb3  mov     r14, rdx
0x14002bcb6  call    cs:__imp_ExAllocateFromPagedLookasideList
0x14002bcbd  nop     dword ptr [rax+rax+00h]
0x14002bcc2  mov     rbx, rax
0x14002bcc5  test    rax, rax
0x14002bcc8  jz      short loc_14002BD0A
0x14002bcca  xor     edx, edx; Val
0x14002bccc  mov     rcx, rax; void *
0x14002bccf  lea     r8d, [rdx+50h]; Size
0x14002bcd3  call    memset
0x14002bcd8  mov     [rbx+10h], edi
0x14002bcdb  mov     [rbx+20h], rbp
0x14002bcdf  mov     [rbx+28h], r14
0x14002bce3  mov     rax, [rsi+8]
0x14002bce7  cmp     [rax], rsi
0x14002bcea  jnz     short loc_14002BD61
0x14002bcec  mov     [rbx], rsi
0x14002bcef  xor     edi, edi
0x14002bcf1  mov     [rbx+8], rax
0x14002bcf5  mov     [rax], rbx
0x14002bcf8  mov     [rsi+8], rbx
0x14002bcfc  mov     eax, edi
0x14002bcfe  add     rsp, 40h
0x14002bd02  pop     r14
0x14002bd04  pop     rdi
0x14002bd05  pop     rsi
0x14002bd06  pop     rbp
0x14002bd07  pop     rbx
0x14002bd08  retn
0x14002bd0a  mov     edi, 0C000009Ah
0x14002bd0f  lea     rax, WPP_RECORDER_INITIALIZED
0x14002bd16  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002bd1d  jz      short loc_14002BCFC
0x14002bd1f  mov     rcx, cs:wil_details_featureDescriptors_a
0x14002bd26  lea     rax, aOnecoreBaseFsW_0; "onecore\\base\\fs\\wci\\wcifs\\dir.c"
0x14002bd2d  mov     [rsp+68h+var_30], edi
0x14002bd31  mov     r9d, 15h
0x14002bd37  mov     [rsp+68h+var_38], 56Fh
0x14002bd3f  mov     dl, 2
0x14002bd41  mov     [rsp+68h+var_40], rax
0x14002bd46  lea     rax, WPP_c1e0b6795ecc304cffe05d8888ed3789_Traceguids
0x14002bd4d  mov     rcx, [rcx+40h]
0x14002bd51  lea     r8d, [r9-3]
0x14002bd55  mov     [rsp+68h+var_48], rax
0x14002bd5a  call    WPP_RECORDER_SF_sDd
0x14002bd5f  jmp     short loc_14002BCFC
0x14002bd61  mov     ecx, 3
0x14002bd66  int     29h; Win8: RtlFailFast(ecx)
```
