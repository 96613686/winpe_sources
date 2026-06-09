# BasepSxsGetLanguageFallbacks

- ea: `0x180001340`
- end: `0x18000143a`
- name: `BasepSxsGetLanguageFallbacks`
- size: `250`
- prototype: `__int64 __fastcall(unsigned int, __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180001440`

## callees

- `0x180001340`

## import_xrefs

- `ntdll!RtlGetThreadPreferredUILanguages` at `0x18000137b`
- `ntdll!RtlGetThreadPreferredUILanguages` at `0x180001408`
- `ntdll!RtlGetThreadPreferredUILanguages` at `0x18000137b`
- `ntdll!RtlGetThreadPreferredUILanguages` at `0x180001408`
- `ntdll!RtlpEnsureBufferSize` at `0x1800013db`
- `ntdll!RtlpEnsureBufferSize` at `0x1800013db`

## pseudocode

```c
__int64 __fastcall BasepSxsGetLanguageFallbacks(unsigned int a1, __int64 a2)
{
  __int64 v2; // r8
  __int64 result; // rax
  unsigned int v5; // edx
  SIZE_T v6; // r8
  __int64 *v7; // rsi
  __int16 *v8; // rdi
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
    {
LABEL_13:
      *(_WORD *)a2 = 2 * v5;
      return result;
    }
  }
  v6 = 2LL * v5 + 2;
  if ( v6 > 0xFFFE )
    return 3221225734LL;
  v7 = (__int64 *)(a2 + 16);
  v8 = (__int16 *)(a2 + 32);
  if ( a2 != -16 && v6 <= *(_QWORD *)v8 || RtlpEnsureBufferSize(0, (PRTL_BUFFER)(a2 + 16), v6) >= 0 )
  {
    v9 = *v7;
    v10 = *v8;
    *(_QWORD *)(a2 + 8) = *v7;
    *(_WORD *)(a2 + 2) = v10;
    result = RtlGetThreadPreferredUILanguages(65544, &v12, v9, &v11);
    if ( (int)result < 0 )
      return result;
    LOWORD(v5) = v11;
    goto LABEL_13;
  }
  return 3221225495LL;
}

```

## disassembly

```asm
0x180001340  mov     [rsp+arg_10], rbx
0x180001345  mov     [rsp+arg_18], rsi
0x18000134a  mov     [rsp+arg_0], ecx
0x18000134e  push    rdi
0x18000134f  sub     rsp, 20h
0x180001353  movzx   eax, word ptr [rdx+2]
0x180001357  lea     r9, [rsp+28h+arg_0]
0x18000135c  mov     r8, [rdx+8]
0x180001360  mov     rbx, rdx
0x180001363  shr     eax, 1
0x180001365  lea     rdx, [rsp+28h+arg_8]
0x18000136a  mov     ecx, 10008h
0x18000136f  mov     [rsp+28h+arg_0], eax
0x180001373  mov     [rsp+28h+arg_8], 0
0x18000137b  call    cs:__imp_RtlGetThreadPreferredUILanguages
0x180001382  nop     dword ptr [rax+rax+00h]
0x180001387  cmp     eax, 0C0000023h
0x18000138c  jz      short loc_1800013A6
0x18000138e  test    eax, eax
0x180001390  js      loc_180001429
0x180001396  movzx   ecx, word ptr [rbx+2]
0x18000139a  mov     edx, [rsp+28h+arg_0]
0x18000139e  shr     ecx, 1
0x1800013a0  cmp     edx, ecx
0x1800013a2  ja      short loc_1800013AA
0x1800013a4  jmp     short loc_18000141C
0x1800013a6  mov     edx, [rsp+28h+arg_0]
0x1800013aa  mov     eax, edx
0x1800013ac  lea     r8, ds:2[rax*2]; RequiredSize
0x1800013b4  cmp     r8, 0FFFEh
0x1800013bb  jbe     short loc_1800013C4
0x1800013bd  mov     eax, 0C0000106h
0x1800013c2  jmp     short loc_180001429
0x1800013c4  lea     rsi, [rbx+10h]
0x1800013c8  lea     rdi, [rbx+20h]
0x1800013cc  test    rsi, rsi
0x1800013cf  jz      short loc_1800013D6
0x1800013d1  cmp     r8, [rdi]
0x1800013d4  jbe     short loc_1800013EB
0x1800013d6  mov     rdx, rsi; Buffer
0x1800013d9  xor     ecx, ecx; Flags
0x1800013db  call    cs:__imp_RtlpEnsureBufferSize
0x1800013e2  nop     dword ptr [rax+rax+00h]
0x1800013e7  test    eax, eax
0x1800013e9  js      short loc_180001424
0x1800013eb  mov     r8, [rsi]
0x1800013ee  lea     r9, [rsp+28h+arg_0]
0x1800013f3  movzx   eax, word ptr [rdi]
0x1800013f6  lea     rdx, [rsp+28h+arg_8]
0x1800013fb  mov     ecx, 10008h
0x180001400  mov     [rbx+8], r8
0x180001404  mov     [rbx+2], ax
0x180001408  call    cs:__imp_RtlGetThreadPreferredUILanguages
0x18000140f  nop     dword ptr [rax+rax+00h]
0x180001414  test    eax, eax
0x180001416  js      short loc_180001429
0x180001418  mov     edx, [rsp+28h+arg_0]
0x18000141c  add     dx, dx
0x18000141f  mov     [rbx], dx
0x180001422  jmp     short loc_180001429
0x180001424  mov     eax, 0C0000017h
0x180001429  mov     rbx, [rsp+28h+arg_10]
0x18000142e  mov     rsi, [rsp+28h+arg_18]
0x180001433  add     rsp, 20h
0x180001437  pop     rdi
0x180001438  retn
```
