# ValidateMSXUPayloadsFieldOfView2(_HW_DEVICE_EXTENSION *,uchar const *,ushort)

- ea: `0x14005abc0`
- end: `0x14005ad1d`
- name: `?ValidateMSXUPayloadsFieldOfView2@@YAJPEAU_HW_DEVICE_EXTENSION@@PEBEG@Z`
- size: `349`
- prototype: `__int64 __fastcall(struct _HW_DEVICE_EXTENSION *, const unsigned __int8 *, unsigned __int16)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x140004bac`
- `0x1400051e4`
- `0x14003b498`
- `0x14005abc0`

## pseudocode

```c
__int64 __fastcall ValidateMSXUPayloadsFieldOfView2(
        struct _HW_DEVICE_EXTENSION *a1,
        const unsigned __int8 *a2,
        unsigned __int16 a3)
{
  __int64 v3; // r10
  int v5; // edx
  const unsigned __int8 *v6; // rbx
  const unsigned __int8 *v7; // r11
  unsigned int v8; // r11d
  _DWORD *v9; // r10
  unsigned int v10; // r11d
  int v11; // ebx
  __int64 v12; // r8
  unsigned int v13; // edx

  v3 = *((_QWORD *)a1 + 134);
  if ( !v3
    || (v5 = *((unsigned __int16 *)a1 + 627), !(_WORD)v5)
    || (v6 = &a2[a3]) == 0
    || !a2
    || (v7 = &a2[2 * a3]) == 0
    || a3 < 4u )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 64, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids);
    return (unsigned int)-1073741436;
  }
  v8 = *(_DWORD *)v7;
  v9 = (_DWORD *)((unsigned int)(2 * v5) + v3);
  if ( v8 != *v9 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      WPP_SF_dd(WPP_GLOBAL_Control->AttachedDevice, 65, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids, v8, *v9);
    return (unsigned int)-1073741436;
  }
  v10 = *(_DWORD *)v6;
  v11 = v9[1];
  v12 = (unsigned int)((v5 - 4) / 4 - 1);
  if ( v10 != v11 || (v13 = 0, *(_DWORD *)a2 != v9[v12 + 1]) )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      WPP_SF_LLLL(
        WPP_GLOBAL_Control->AttachedDevice,
        (unsigned int)v9[v12 + 1],
        v12,
        v10,
        v11,
        *(_DWORD *)a2,
        v9[v12 + 1]);
    return (unsigned int)-1073741436;
  }
  return v13;
}

```

## disassembly

```asm
0x14005abc0  mov     [rsp+arg_0], rbx
0x14005abc5  mov     [rsp+arg_8], rsi
0x14005abca  push    rdi
0x14005abcb  sub     rsp, 40h
0x14005abcf  mov     r10, [rcx+430h]
0x14005abd6  xor     edi, edi
0x14005abd8  mov     r9, rdx
0x14005abdb  test    r10, r10
0x14005abde  jz      loc_14005ACD7
0x14005abe4  movzx   edx, word ptr [rcx+4E6h]
0x14005abeb  test    dx, dx
0x14005abee  jz      loc_14005ACD7
0x14005abf4  movzx   ebx, r8w
0x14005abf8  add     rbx, r9
0x14005abfb  jz      loc_14005ACD7
0x14005ac01  test    r9, r9
0x14005ac04  jz      loc_14005ACD7
0x14005ac0a  movzx   eax, r8w
0x14005ac0e  lea     r11d, [rax+rax]
0x14005ac12  add     r11, r9
0x14005ac15  jz      loc_14005ACD7
0x14005ac1b  lea     esi, [rdi+4]
0x14005ac1e  cmp     r8w, si
0x14005ac22  jb      loc_14005ACD7
0x14005ac28  mov     r11d, [r11]
0x14005ac2b  lea     ecx, [rdx+rdx]
0x14005ac2e  add     r10, rcx
0x14005ac31  mov     r8d, [r10]
0x14005ac34  cmp     r11d, r8d
0x14005ac37  jz      short loc_14005AC7A
0x14005ac39  mov     rcx, cs:WPP_GLOBAL_Control
0x14005ac40  lea     rax, WPP_GLOBAL_Control
0x14005ac47  cmp     rcx, rax
0x14005ac4a  jz      loc_14005AD05
0x14005ac50  cmp     byte ptr [rcx+29h], 2
0x14005ac54  jb      loc_14005AD05
0x14005ac5a  mov     rcx, [rcx+18h]
0x14005ac5e  lea     edx, [rdi+41h]
0x14005ac61  mov     [rsp+48h+var_28], r8d
0x14005ac66  mov     r9d, r11d
0x14005ac69  lea     r8, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids
0x14005ac70  call    WPP_SF_dd
0x14005ac75  jmp     loc_14005AD05
0x14005ac7a  mov     r11d, [rbx]
0x14005ac7d  lea     eax, [rdx-4]
0x14005ac80  mov     ebx, [r10+4]
0x14005ac84  cdq
0x14005ac85  idiv    esi
0x14005ac87  lea     r8d, [rax-1]
0x14005ac8b  cmp     r11d, ebx
0x14005ac8e  jnz     short loc_14005AC9C
0x14005ac90  mov     ecx, [r10+r8*4+4]
0x14005ac95  mov     edx, edi
0x14005ac97  cmp     [r9], ecx
0x14005ac9a  jz      short loc_14005AD0A
0x14005ac9c  mov     rcx, cs:WPP_GLOBAL_Control
0x14005aca3  lea     rax, WPP_GLOBAL_Control
0x14005acaa  cmp     rcx, rax
0x14005acad  jz      short loc_14005AD05
0x14005acaf  cmp     byte ptr [rcx+29h], 2
0x14005acb3  jb      short loc_14005AD05
0x14005acb5  mov     eax, [r9]
0x14005acb8  mov     r9d, r11d
0x14005acbb  mov     edx, [r10+r8*4+4]
0x14005acc0  mov     rcx, [rcx+18h]
0x14005acc4  mov     [rsp+48h+var_18], edx
0x14005acc8  mov     [rsp+48h+var_20], eax
0x14005accc  mov     [rsp+48h+var_28], ebx
0x14005acd0  call    WPP_SF_LLLL
0x14005acd5  jmp     short loc_14005AD05
0x14005acd7  mov     rcx, cs:WPP_GLOBAL_Control
0x14005acde  lea     rax, WPP_GLOBAL_Control
0x14005ace5  cmp     rcx, rax
0x14005ace8  jz      short loc_14005AD05
0x14005acea  cmp     byte ptr [rcx+29h], 2
0x14005acee  jb      short loc_14005AD05
0x14005acf0  mov     rcx, [rcx+18h]
0x14005acf4  lea     r8, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids
0x14005acfb  mov     edx, 40h ; '@'
0x14005ad00  call    WPP_SF_
0x14005ad05  mov     edx, 0C0000184h
0x14005ad0a  mov     rbx, [rsp+48h+arg_0]
0x14005ad0f  mov     eax, edx
0x14005ad11  mov     rsi, [rsp+48h+arg_8]
0x14005ad16  add     rsp, 40h
0x14005ad1a  pop     rdi
0x14005ad1b  retn
```
