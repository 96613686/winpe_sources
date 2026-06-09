# BasepSxsGetLanguageFallbacks

- ea: `0x180001350`
- end: `0x18000144a`
- name: `BasepSxsGetLanguageFallbacks`
- size: `250`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180001450`

## callees

- `0x180001350`

## import_xrefs

- `ntdll!RtlGetThreadPreferredUILanguages` at `0x18000138b`
- `ntdll!RtlGetThreadPreferredUILanguages` at `0x18000141f`
- `ntdll!RtlGetThreadPreferredUILanguages` at `0x18000138b`
- `ntdll!RtlGetThreadPreferredUILanguages` at `0x18000141f`
- `ntdll!RtlpEnsureBufferSize` at `0x1800013eb`
- `ntdll!RtlpEnsureBufferSize` at `0x1800013eb`

## pseudocode

```c
__int64 __fastcall BasepSxsGetLanguageFallbacks(unsigned int a1, __int64 a2)
{
  __int64 v2; // r8
  __int64 result; // rax
  unsigned int v5; // edx
  SIZE_T v6; // r8
  __int64 *v7; // rsi
  SIZE_T *v8; // rdi
  __int64 v9; // r8
  __int16 v10; // ax
  unsigned int v11; // [rsp+30h] [rbp+8h] BYREF
  int v12; // [rsp+38h] [rbp+10h] BYREF

  v11 = a1;
  v2 = *(_QWORD *)(a2 + 8);
  v11 = *(unsigned __int16 *)(a2 + 2) >> 1;
  v12 = 0;
  result = RtlGetThreadPreferredUILanguages(65544, &v12, v2, &v11);
  if ( (_DWORD)result == -1073741789 )
  {
    v5 = v11;
  }
  else
  {
    if ( (int)result < 0 )
      return result;
    v5 = v11;
    if ( v11 <= *(unsigned __int16 *)(a2 + 2) >> 1 )
      goto LABEL_14;
  }
  v6 = 2LL * v5 + 2;
  if ( v6 > 0xFFFE )
    return 3221225734LL;
  v7 = (__int64 *)(a2 + 16);
  v8 = (SIZE_T *)(a2 + 32);
  if ( (a2 == -16 || v6 > *v8) && RtlpEnsureBufferSize(0, (PRTL_BUFFER)(a2 + 16), v6) < 0 )
    return 3221225495LL;
  v9 = *v7;
  v10 = *(_WORD *)v8;
  *(_QWORD *)(a2 + 8) = *v7;
  *(_WORD *)(a2 + 2) = v10;
  result = RtlGetThreadPreferredUILanguages(65544, &v12, v9, &v11);
  if ( (int)result >= 0 )
  {
    LOWORD(v5) = v11;
LABEL_14:
    *(_WORD *)a2 = 2 * v5;
  }
  return result;
}

```

## disassembly

```asm
0x180001350  mov     [rsp+arg_10], rbx
0x180001355  mov     [rsp+arg_18], rsi
0x18000135a  mov     [rsp+arg_0], ecx
0x18000135e  push    rdi
0x18000135f  sub     rsp, 20h
0x180001363  movzx   eax, word ptr [rdx+2]
0x180001367  lea     r9, [rsp+28h+arg_0]
0x18000136c  mov     r8, [rdx+8]
0x180001370  mov     rbx, rdx
0x180001373  shr     eax, 1
0x180001375  lea     rdx, [rsp+28h+arg_8]
0x18000137a  mov     ecx, 10008h
0x18000137f  mov     [rsp+28h+arg_0], eax
0x180001383  mov     [rsp+28h+arg_8], 0
0x18000138b  call    cs:__imp_RtlGetThreadPreferredUILanguages
0x180001392  nop     dword ptr [rax+rax+00h]
0x180001397  cmp     eax, 0C0000023h
0x18000139c  jz      short loc_1800013B6
0x18000139e  test    eax, eax
0x1800013a0  js      loc_180001439
0x1800013a6  movzx   ecx, word ptr [rbx+2]
0x1800013aa  mov     edx, [rsp+28h+arg_0]
0x1800013ae  shr     ecx, 1
0x1800013b0  cmp     edx, ecx
0x1800013b2  ja      short loc_1800013BA
0x1800013b4  jmp     short loc_180001433
0x1800013b6  mov     edx, [rsp+28h+arg_0]
0x1800013ba  mov     eax, edx
0x1800013bc  lea     r8, ds:2[rax*2]; RequiredSize
0x1800013c4  cmp     r8, 0FFFEh
0x1800013cb  jbe     short loc_1800013D4
0x1800013cd  mov     eax, 0C0000106h
0x1800013d2  jmp     short loc_180001439
0x1800013d4  lea     rsi, [rbx+10h]
0x1800013d8  lea     rdi, [rbx+20h]
0x1800013dc  test    rsi, rsi
0x1800013df  jz      short loc_1800013E6
0x1800013e1  cmp     r8, [rdi]
0x1800013e4  jbe     short loc_180001402
0x1800013e6  mov     rdx, rsi; Buffer
0x1800013e9  xor     ecx, ecx; Flags
0x1800013eb  call    cs:__imp_RtlpEnsureBufferSize
0x1800013f2  nop     dword ptr [rax+rax+00h]
0x1800013f7  test    eax, eax
0x1800013f9  jns     short loc_180001402
0x1800013fb  mov     eax, 0C0000017h
0x180001400  jmp     short loc_180001439
0x180001402  mov     r8, [rsi]
0x180001405  lea     r9, [rsp+28h+arg_0]
0x18000140a  movzx   eax, word ptr [rdi]
0x18000140d  lea     rdx, [rsp+28h+arg_8]
0x180001412  mov     ecx, 10008h
0x180001417  mov     [rbx+8], r8
0x18000141b  mov     [rbx+2], ax
0x18000141f  call    cs:__imp_RtlGetThreadPreferredUILanguages
0x180001426  nop     dword ptr [rax+rax+00h]
0x18000142b  test    eax, eax
0x18000142d  js      short loc_180001439
0x18000142f  mov     edx, [rsp+28h+arg_0]
0x180001433  add     dx, dx
0x180001436  mov     [rbx], dx
0x180001439  mov     rbx, [rsp+28h+arg_10]
0x18000143e  mov     rsi, [rsp+28h+arg_18]
0x180001443  add     rsp, 20h
0x180001447  pop     rdi
0x180001448  retn
```
