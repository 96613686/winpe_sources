# WcAddSubContext

- ea: `0x14002bc48`
- end: `0x14002bd18`
- name: `WcAddSubContext`
- size: `208`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x14002b9f0`

## callees

- `0x1400020c4`
- `0x1400080c0`
- `0x14002bc48`

## import_xrefs

- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x14002bc66`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x14002bc66`

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
        WPP_GLOBAL_Control->DeviceExtension,
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
0x14002bc48  push    rbx
0x14002bc4a  push    rbp
0x14002bc4b  push    rsi
0x14002bc4c  push    rdi
0x14002bc4d  push    r14
0x14002bc4f  sub     rsp, 40h
0x14002bc53  mov     rsi, rcx
0x14002bc56  mov     edi, r9d
0x14002bc59  lea     rcx, Lookaside; Lookaside
0x14002bc60  mov     rbp, r8
0x14002bc63  mov     r14, rdx
0x14002bc66  call    cs:__imp_ExAllocateFromPagedLookasideList
0x14002bc6d  nop     dword ptr [rax+rax+00h]
0x14002bc72  mov     rbx, rax
0x14002bc75  test    rax, rax
0x14002bc78  jz      short loc_14002BCBA
0x14002bc7a  xor     edx, edx; Val
0x14002bc7c  mov     rcx, rax; void *
0x14002bc7f  lea     r8d, [rdx+50h]; Size
0x14002bc83  call    memset
0x14002bc88  mov     [rbx+10h], edi
0x14002bc8b  mov     [rbx+20h], rbp
0x14002bc8f  mov     [rbx+28h], r14
0x14002bc93  mov     rax, [rsi+8]
0x14002bc97  cmp     [rax], rsi
0x14002bc9a  jnz     short loc_14002BD11
0x14002bc9c  mov     [rbx], rsi
0x14002bc9f  xor     edi, edi
0x14002bca1  mov     [rbx+8], rax
0x14002bca5  mov     [rax], rbx
0x14002bca8  mov     [rsi+8], rbx
0x14002bcac  mov     eax, edi
0x14002bcae  add     rsp, 40h
0x14002bcb2  pop     r14
0x14002bcb4  pop     rdi
0x14002bcb5  pop     rsi
0x14002bcb6  pop     rbp
0x14002bcb7  pop     rbx
0x14002bcb8  retn
0x14002bcba  mov     edi, 0C000009Ah
0x14002bcbf  lea     rax, WPP_RECORDER_INITIALIZED
0x14002bcc6  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002bccd  jz      short loc_14002BCAC
0x14002bccf  mov     rcx, cs:WPP_GLOBAL_Control
0x14002bcd6  lea     rax, aOnecoreBaseFsW_0; "onecore\\base\\fs\\wci\\wcifs\\dir.c"
0x14002bcdd  mov     [rsp+68h+var_30], edi
0x14002bce1  mov     r9d, 15h
0x14002bce7  mov     [rsp+68h+var_38], 56Fh
0x14002bcef  mov     dl, 2
0x14002bcf1  mov     [rsp+68h+var_40], rax
0x14002bcf6  lea     rax, WPP_c1e0b6795ecc304cffe05d8888ed3789_Traceguids
0x14002bcfd  mov     rcx, [rcx+40h]
0x14002bd01  lea     r8d, [r9-3]
0x14002bd05  mov     [rsp+68h+var_48], rax
0x14002bd0a  call    WPP_RECORDER_SF_sDd
0x14002bd0f  jmp     short loc_14002BCAC
0x14002bd11  mov     ecx, 3
0x14002bd16  int     29h; Win8: RtlFailFast(ecx)
```
