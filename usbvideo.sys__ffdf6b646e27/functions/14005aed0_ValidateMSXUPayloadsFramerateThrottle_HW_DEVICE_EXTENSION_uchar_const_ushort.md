# ValidateMSXUPayloadsFramerateThrottle(_HW_DEVICE_EXTENSION *,uchar const *,ushort)

- ea: `0x14005aed0`
- end: `0x14005b00f`
- name: `?ValidateMSXUPayloadsFramerateThrottle@@YAJPEAU_HW_DEVICE_EXTENSION@@PEBEG@Z`
- size: `319`
- prototype: `__int64 __fastcall(struct _HW_DEVICE_EXTENSION *, const unsigned __int8 *, unsigned __int16)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x14003b1ec`
- `0x14005aed0`

## pseudocode

```c
__int64 __fastcall ValidateMSXUPayloadsFramerateThrottle(
        struct _HW_DEVICE_EXTENSION *a1,
        const unsigned __int8 *a2,
        unsigned __int16 a3)
{
  __int64 v3; // rax
  __int64 v4; // rdi
  __int64 v6; // rsi
  unsigned int v7; // ecx
  unsigned int v8; // r8d
  unsigned int v9; // r8d
  unsigned int v10; // eax
  unsigned int v11; // ecx

  v3 = 2 * (unsigned int)a3;
  v4 = a3;
  v6 = v3;
  if ( *(_DWORD *)&a2[v3]
    || *(_DWORD *)&a2[v3 + 4] != 100
    || *(_DWORD *)&a2[v3 + 12] != 100
    || (v7 = *(_DWORD *)&a2[v3 + 8]) == 0
    || *(_DWORD *)&a2[a3 + 8] >= *(_DWORD *)&a2[a3 + 12]
    || (v8 = *(_DWORD *)&a2[v3 + 16], v7 % v8)
    || 0x64 % v8 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      WPP_SF_LLLLL(WPP_GLOBAL_Control->AttachedDevice, 57);
    v9 = -1073741436;
  }
  else
  {
    v9 = 0;
  }
  if ( *(_DWORD *)&a2[v4] != 1
    || *(_DWORD *)&a2[v4 + 4] != 100
    || *(_DWORD *)&a2[v4 + 12] != 100
    || (v10 = *(_DWORD *)&a2[v4 + 8], v10 - 1 > 0x62)
    || (v11 = *(_DWORD *)&a2[v6 + 16], v10 % v11)
    || 0x64 % v11 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      WPP_SF_LLLLL(WPP_GLOBAL_Control->AttachedDevice, 58);
    return (unsigned int)-1073741436;
  }
  return v9;
}

```

## disassembly

```asm
0x14005aed0  push    rbx
0x14005aed2  push    rsi
0x14005aed3  push    rdi
0x14005aed4  push    r15
0x14005aed6  sub     rsp, 48h
0x14005aeda  movzx   eax, r8w
0x14005aede  lea     r15, WPP_GLOBAL_Control
0x14005aee5  add     eax, eax
0x14005aee7  movzx   edi, r8w
0x14005aeeb  mov     rbx, rdx
0x14005aeee  mov     esi, eax
0x14005aef0  mov     r9d, [rax+rdx]
0x14005aef4  test    r9d, r9d
0x14005aef7  jnz     short loc_14005AF3A
0x14005aef9  cmp     dword ptr [rax+rdx+4], 64h ; 'd'
0x14005aefe  jnz     short loc_14005AF3A
0x14005af00  cmp     dword ptr [rax+rdx+0Ch], 64h ; 'd'
0x14005af05  jnz     short loc_14005AF3A
0x14005af07  mov     ecx, [rax+rdx+8]
0x14005af0b  test    ecx, ecx
0x14005af0d  jz      short loc_14005AF3A
0x14005af0f  mov     eax, [rdi+rdx+0Ch]
0x14005af13  cmp     [rdi+rdx+8], eax
0x14005af17  jnb     short loc_14005AF3A
0x14005af19  mov     r8d, [rsi+rdx+10h]
0x14005af1e  mov     eax, ecx
0x14005af20  xor     edx, edx
0x14005af22  div     r8d
0x14005af25  test    edx, edx
0x14005af27  jnz     short loc_14005AF3A
0x14005af29  xor     edx, edx
0x14005af2b  lea     eax, [rdx+64h]
0x14005af2e  div     r8d
0x14005af31  test    edx, edx
0x14005af33  jnz     short loc_14005AF3A
0x14005af35  xor     r8d, r8d
0x14005af38  jmp     short loc_14005AF80
0x14005af3a  mov     rcx, cs:WPP_GLOBAL_Control
0x14005af41  cmp     rcx, r15
0x14005af44  jz      short loc_14005AF7A
0x14005af46  cmp     byte ptr [rcx+29h], 2
0x14005af4a  jb      short loc_14005AF7A
0x14005af4c  mov     eax, [rsi+rbx+10h]
0x14005af50  mov     edx, 39h ; '9'
0x14005af55  mov     rcx, [rcx+18h]
0x14005af59  mov     [rsp+68h+var_30], eax
0x14005af5d  mov     eax, [rsi+rbx+0Ch]
0x14005af61  mov     [rsp+68h+var_38], eax
0x14005af65  mov     eax, [rsi+rbx+8]
0x14005af69  mov     [rsp+68h+var_40], eax
0x14005af6d  mov     eax, [rsi+rbx+4]
0x14005af71  mov     [rsp+68h+var_48], eax
0x14005af75  call    WPP_SF_LLLLL
0x14005af7a  mov     r8d, 0C0000184h
0x14005af80  mov     r9d, [rdi+rbx]
0x14005af84  cmp     r9d, 1
0x14005af88  jnz     short loc_14005AFBB
0x14005af8a  cmp     dword ptr [rdi+rbx+4], 64h ; 'd'
0x14005af8f  jnz     short loc_14005AFBB
0x14005af91  cmp     dword ptr [rdi+rbx+0Ch], 64h ; 'd'
0x14005af96  jnz     short loc_14005AFBB
0x14005af98  mov     eax, [rdi+rbx+8]
0x14005af9c  lea     ecx, [rax-1]
0x14005af9f  cmp     ecx, 62h ; 'b'
0x14005afa2  ja      short loc_14005AFBB
0x14005afa4  mov     ecx, [rsi+rbx+10h]
0x14005afa8  xor     edx, edx
0x14005afaa  div     ecx
0x14005afac  test    edx, edx
0x14005afae  jnz     short loc_14005AFBB
0x14005afb0  xor     edx, edx
0x14005afb2  lea     eax, [rdx+64h]
0x14005afb5  div     ecx
0x14005afb7  test    edx, edx
0x14005afb9  jz      short loc_14005B001
0x14005afbb  mov     rcx, cs:WPP_GLOBAL_Control
0x14005afc2  cmp     rcx, r15
0x14005afc5  jz      short loc_14005AFFB
0x14005afc7  cmp     byte ptr [rcx+29h], 2
0x14005afcb  jb      short loc_14005AFFB
0x14005afcd  mov     eax, [rdi+rbx+10h]
0x14005afd1  mov     edx, 3Ah ; ':'
0x14005afd6  mov     rcx, [rcx+18h]
0x14005afda  mov     [rsp+68h+var_30], eax
0x14005afde  mov     eax, [rdi+rbx+0Ch]
0x14005afe2  mov     [rsp+68h+var_38], eax
0x14005afe6  mov     eax, [rdi+rbx+8]
0x14005afea  mov     [rsp+68h+var_40], eax
0x14005afee  mov     eax, [rdi+rbx+4]
0x14005aff2  mov     [rsp+68h+var_48], eax
0x14005aff6  call    WPP_SF_LLLLL
0x14005affb  mov     r8d, 0C0000184h
0x14005b001  mov     eax, r8d
0x14005b004  add     rsp, 48h
0x14005b008  pop     r15
0x14005b00a  pop     rdi
0x14005b00b  pop     rsi
0x14005b00c  pop     rbx
0x14005b00d  retn
```
