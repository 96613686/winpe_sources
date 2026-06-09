# ValidateMSXUPayloadsDigitalWindow(_HW_DEVICE_EXTENSION *,uchar const *,ushort)

- ea: `0x14005a5c0`
- end: `0x14005a709`
- name: `?ValidateMSXUPayloadsDigitalWindow@@YAJPEAU_HW_DEVICE_EXTENSION@@PEBEG@Z`
- size: `329`
- prototype: `__int64 __fastcall(struct _HW_DEVICE_EXTENSION *, const unsigned __int8 *, unsigned __int16)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x1400053fc`
- `0x14005a5c0`

## pseudocode

```c
__int64 __fastcall ValidateMSXUPayloadsDigitalWindow(
        struct _HW_DEVICE_EXTENSION *a1,
        const unsigned __int8 *a2,
        unsigned __int16 a3)
{
  __int64 v4; // rsi
  __int64 v5; // rdi
  __int64 result; // rax

  v4 = 3 * (unsigned int)a3;
  v5 = 2 * (unsigned int)a3;
  if ( (*(_QWORD *)a2 || *((_DWORD *)a2 + 2) || *((_DWORD *)a2 + 3) != 0x1000000)
    && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
  {
    WPP_SF_DDDD(
      WPP_GLOBAL_Control->AttachedDevice,
      51,
      WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids,
      *(unsigned int *)a2,
      *((_DWORD *)a2 + 1),
      *((_DWORD *)a2 + 2),
      *((_DWORD *)a2 + 3));
  }
  if ( (*(_QWORD *)&a2[v4] || *(_DWORD *)&a2[v4 + 8] || *(_DWORD *)&a2[v4 + 12] != 0x1000000)
    && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
  {
    WPP_SF_DDDD(
      WPP_GLOBAL_Control->AttachedDevice,
      52,
      WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids,
      *(unsigned int *)&a2[v4],
      *(_DWORD *)&a2[v4 + 4],
      *(_DWORD *)&a2[v4 + 8],
      *(_DWORD *)&a2[v4 + 12]);
  }
  if ( *(_QWORD *)&a2[v5] || *(_DWORD *)&a2[v5 + 8] || (result = 0, *(_DWORD *)&a2[v5 + 12] != 0x1000000) )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      WPP_SF_DDDD(
        WPP_GLOBAL_Control->AttachedDevice,
        53,
        WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids,
        *(unsigned int *)&a2[v5],
        *(_DWORD *)&a2[v5 + 4],
        *(_DWORD *)&a2[v5 + 8],
        *(_DWORD *)&a2[v5 + 12]);
    return 3221225860LL;
  }
  return result;
}

```

## disassembly

```asm
0x14005a5c0  push    rbx
0x14005a5c2  push    rsi
0x14005a5c3  push    rdi
0x14005a5c4  push    r15
0x14005a5c6  sub     rsp, 48h
0x14005a5ca  mov     r9d, [rdx]
0x14005a5cd  lea     r15, WPP_GLOBAL_Control
0x14005a5d4  movzx   ecx, r8w
0x14005a5d8  mov     rbx, rdx
0x14005a5db  lea     esi, [rcx+rcx*2]
0x14005a5de  lea     edi, [rcx+rcx]
0x14005a5e1  test    r9d, r9d
0x14005a5e4  jnz     short loc_14005A5FB
0x14005a5e6  cmp     [rdx+4], r9d
0x14005a5ea  jnz     short loc_14005A5FB
0x14005a5ec  cmp     [rdx+8], r9d
0x14005a5f0  jnz     short loc_14005A5FB
0x14005a5f2  cmp     dword ptr [rdx+0Ch], 1000000h
0x14005a5f9  jz      short loc_14005A637
0x14005a5fb  mov     rcx, cs:WPP_GLOBAL_Control
0x14005a602  cmp     rcx, r15
0x14005a605  jz      short loc_14005A637
0x14005a607  cmp     byte ptr [rcx+29h], 3
0x14005a60b  jb      short loc_14005A637
0x14005a60d  mov     eax, [rbx+0Ch]
0x14005a610  lea     r8, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids
0x14005a617  mov     rcx, [rcx+18h]
0x14005a61b  mov     edx, 33h ; '3'
0x14005a620  mov     [rsp+68h+var_38], eax
0x14005a624  mov     eax, [rbx+8]
0x14005a627  mov     [rsp+68h+var_40], eax
0x14005a62b  mov     eax, [rbx+4]
0x14005a62e  mov     [rsp+68h+var_48], eax
0x14005a632  call    WPP_SF_DDDD
0x14005a637  mov     r9d, [rsi+rbx]
0x14005a63b  test    r9d, r9d
0x14005a63e  jnz     short loc_14005A658
0x14005a640  cmp     [rsi+rbx+4], r9d
0x14005a645  jnz     short loc_14005A658
0x14005a647  cmp     [rsi+rbx+8], r9d
0x14005a64c  jnz     short loc_14005A658
0x14005a64e  cmp     dword ptr [rsi+rbx+0Ch], 1000000h
0x14005a656  jz      short loc_14005A697
0x14005a658  mov     rcx, cs:WPP_GLOBAL_Control
0x14005a65f  cmp     rcx, r15
0x14005a662  jz      short loc_14005A697
0x14005a664  cmp     byte ptr [rcx+29h], 3
0x14005a668  jb      short loc_14005A697
0x14005a66a  mov     eax, [rsi+rbx+0Ch]
0x14005a66e  lea     r8, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids
0x14005a675  mov     rcx, [rcx+18h]
0x14005a679  mov     edx, 34h ; '4'
0x14005a67e  mov     [rsp+68h+var_38], eax
0x14005a682  mov     eax, [rsi+rbx+8]
0x14005a686  mov     [rsp+68h+var_40], eax
0x14005a68a  mov     eax, [rsi+rbx+4]
0x14005a68e  mov     [rsp+68h+var_48], eax
0x14005a692  call    WPP_SF_DDDD
0x14005a697  mov     r9d, [rdi+rbx]
0x14005a69b  test    r9d, r9d
0x14005a69e  jnz     short loc_14005A6BA
0x14005a6a0  cmp     [rdi+rbx+4], r9d
0x14005a6a5  jnz     short loc_14005A6BA
0x14005a6a7  cmp     [rdi+rbx+8], r9d
0x14005a6ac  jnz     short loc_14005A6BA
0x14005a6ae  xor     eax, eax
0x14005a6b0  cmp     dword ptr [rdi+rbx+0Ch], 1000000h
0x14005a6b8  jz      short loc_14005A6FE
0x14005a6ba  mov     rcx, cs:WPP_GLOBAL_Control
0x14005a6c1  cmp     rcx, r15
0x14005a6c4  jz      short loc_14005A6F9
0x14005a6c6  cmp     byte ptr [rcx+29h], 2
0x14005a6ca  jb      short loc_14005A6F9
0x14005a6cc  mov     eax, [rdi+rbx+0Ch]
0x14005a6d0  lea     r8, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids
0x14005a6d7  mov     rcx, [rcx+18h]
0x14005a6db  mov     edx, 35h ; '5'
0x14005a6e0  mov     [rsp+68h+var_38], eax
0x14005a6e4  mov     eax, [rdi+rbx+8]
0x14005a6e8  mov     [rsp+68h+var_40], eax
0x14005a6ec  mov     eax, [rdi+rbx+4]
0x14005a6f0  mov     [rsp+68h+var_48], eax
0x14005a6f4  call    WPP_SF_DDDD
0x14005a6f9  mov     eax, 0C0000184h
0x14005a6fe  add     rsp, 48h
0x14005a702  pop     r15
0x14005a704  pop     rdi
0x14005a705  pop     rsi
0x14005a706  pop     rbx
0x14005a707  retn
```
