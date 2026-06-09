# ValidateMSXUPayloadsFieldOfView2Config(_HW_DEVICE_EXTENSION *,uchar const *,ushort)

- ea: `0x14005ad30`
- end: `0x14005aec1`
- name: `?ValidateMSXUPayloadsFieldOfView2Config@@YAJPEAU_HW_DEVICE_EXTENSION@@PEBEG@Z`
- size: `401`
- prototype: `__int64 __fastcall(struct _HW_DEVICE_EXTENSION *, const unsigned __int8 *, unsigned __int16)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callees

- `0x1400051e4`
- `0x14001b118`
- `0x14005ad30`

## pseudocode

```c
__int64 __fastcall ValidateMSXUPayloadsFieldOfView2Config(
        struct _HW_DEVICE_EXTENSION *a1,
        const unsigned __int8 *a2,
        unsigned __int16 a3)
{
  __int64 v3; // r9
  unsigned int v5; // edx
  unsigned int v6; // ebx
  const unsigned __int8 *v7; // r11
  unsigned int v8; // r10d
  char v9; // cl
  __int64 v10; // r9
  unsigned int v11; // r8d
  PDEVICE_OBJECT v12; // rcx
  __int64 v13; // rdx
  PDEVICE_OBJECT v14; // rcx
  __int64 v15; // rdx

  v3 = *((unsigned __int16 *)a1 + 627);
  if ( (unsigned int)v3 < 8 || (v5 = ((int)v3 - 4) % 4, v6 = ((int)v3 - 4) / 4, v5) )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 59, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids, v3);
  }
  else
  {
    v7 = &a2[2 * a3];
    v8 = *(_DWORD *)v7;
    if ( (unsigned int)(*(_DWORD *)v7 - 1) > 0x167 )
    {
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        v15 = 60;
LABEL_23:
        WPP_SF_d(v14->AttachedDevice, v15, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids, v8);
      }
    }
    else
    {
      v9 = 0;
      v10 = 0;
      while ( (unsigned int)v10 < v6 )
      {
        v11 = *(_DWORD *)&v7[4 * v10 + 4];
        if ( v11 - 1 > 0x167 )
        {
          v12 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          {
            v13 = 61;
            goto LABEL_15;
          }
          return 3221225860LL;
        }
        if ( v11 == v8 )
          v9 = 1;
        if ( (_DWORD)v10 && v5 <= v11 )
        {
          v12 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          {
            v13 = 62;
LABEL_15:
            WPP_SF_dd(v12->AttachedDevice, v13, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids, v10, v11);
            return 3221225860LL;
          }
          return 3221225860LL;
        }
        v10 = (unsigned int)(v10 + 1);
        v5 = v11;
      }
      if ( v9 )
        return 0;
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        v15 = 63;
        goto LABEL_23;
      }
    }
  }
  return 3221225860LL;
}

```

## disassembly

```asm
0x14005ad30  mov     [rsp+arg_0], rbx
0x14005ad35  push    rdi
0x14005ad36  sub     rsp, 30h
0x14005ad3a  movzx   r9d, word ptr [rcx+4E6h]
0x14005ad42  mov     r10, rdx
0x14005ad45  cmp     r9d, 8
0x14005ad49  jb      loc_14005AE82
0x14005ad4f  lea     eax, [r9-4]
0x14005ad53  mov     ecx, 4
0x14005ad58  cdq
0x14005ad59  idiv    ecx
0x14005ad5b  mov     ebx, eax
0x14005ad5d  test    edx, edx
0x14005ad5f  jnz     loc_14005AE82
0x14005ad65  movzx   ecx, r8w
0x14005ad69  lea     r11d, [rcx+rcx]
0x14005ad6d  add     r11, r10
0x14005ad70  mov     r10d, [r11]
0x14005ad73  lea     ecx, [r10-1]
0x14005ad77  cmp     ecx, 167h
0x14005ad7d  ja      loc_14005AE62
0x14005ad83  xor     cl, cl
0x14005ad85  lea     edi, [rdx+1]
0x14005ad88  xor     r9d, r9d
0x14005ad8b  cmp     r9d, ebx
0x14005ad8e  jnb     loc_14005AE27
0x14005ad94  mov     r8d, [r11+r9*4+4]
0x14005ad99  lea     eax, [r8-1]
0x14005ad9d  cmp     eax, 167h
0x14005ada2  ja      short loc_14005ADFF
0x14005ada4  cmp     r8d, r10d
0x14005ada7  movzx   ecx, cl
0x14005adaa  cmovz   ecx, edi
0x14005adad  test    r9d, r9d
0x14005adb0  jz      short loc_14005ADB7
0x14005adb2  cmp     edx, r8d
0x14005adb5  jbe     short loc_14005ADBF
0x14005adb7  add     r9d, edi
0x14005adba  mov     edx, r8d
0x14005adbd  jmp     short loc_14005AD8B
0x14005adbf  mov     rcx, cs:WPP_GLOBAL_Control
0x14005adc6  lea     rax, WPP_GLOBAL_Control
0x14005adcd  cmp     rcx, rax
0x14005add0  jz      loc_14005AEB0
0x14005add6  cmp     byte ptr [rcx+29h], 2
0x14005adda  jb      loc_14005AEB0
0x14005ade0  mov     edx, 3Eh ; '>'
0x14005ade5  mov     rcx, [rcx+18h]
0x14005ade9  mov     [rsp+38h+var_18], r8d
0x14005adee  lea     r8, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids
0x14005adf5  call    WPP_SF_dd
0x14005adfa  jmp     loc_14005AEB0
0x14005adff  mov     rcx, cs:WPP_GLOBAL_Control
0x14005ae06  lea     rax, WPP_GLOBAL_Control
0x14005ae0d  cmp     rcx, rax
0x14005ae10  jz      loc_14005AEB0
0x14005ae16  cmp     byte ptr [rcx+29h], 2
0x14005ae1a  jb      loc_14005AEB0
0x14005ae20  mov     edx, 3Dh ; '='
0x14005ae25  jmp     short loc_14005ADE5
0x14005ae27  test    cl, cl
0x14005ae29  jnz     short loc_14005AE5E
0x14005ae2b  mov     rcx, cs:WPP_GLOBAL_Control
0x14005ae32  lea     rax, WPP_GLOBAL_Control
0x14005ae39  cmp     rcx, rax
0x14005ae3c  jz      short loc_14005AEB0
0x14005ae3e  cmp     byte ptr [rcx+29h], 2
0x14005ae42  jb      short loc_14005AEB0
0x14005ae44  mov     edx, 3Fh ; '?'
0x14005ae49  mov     rcx, [rcx+18h]
0x14005ae4d  lea     r8, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids
0x14005ae54  mov     r9d, r10d
0x14005ae57  call    WPP_SF_d
0x14005ae5c  jmp     short loc_14005AEB0
0x14005ae5e  xor     eax, eax
0x14005ae60  jmp     short loc_14005AEB5
0x14005ae62  mov     rcx, cs:WPP_GLOBAL_Control
0x14005ae69  lea     rax, WPP_GLOBAL_Control
0x14005ae70  cmp     rcx, rax
0x14005ae73  jz      short loc_14005AEB0
0x14005ae75  cmp     byte ptr [rcx+29h], 2
0x14005ae79  jb      short loc_14005AEB0
0x14005ae7b  mov     edx, 3Ch ; '<'
0x14005ae80  jmp     short loc_14005AE49
0x14005ae82  mov     rcx, cs:WPP_GLOBAL_Control
0x14005ae89  lea     rax, WPP_GLOBAL_Control
0x14005ae90  cmp     rcx, rax
0x14005ae93  jz      short loc_14005AEB0
0x14005ae95  cmp     byte ptr [rcx+29h], 2
0x14005ae99  jb      short loc_14005AEB0
0x14005ae9b  mov     rcx, [rcx+18h]
0x14005ae9f  lea     r8, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids
0x14005aea6  mov     edx, 3Bh ; ';'
0x14005aeab  call    WPP_SF_d
0x14005aeb0  mov     eax, 0C0000184h
0x14005aeb5  mov     rbx, [rsp+38h+arg_0]
0x14005aeba  add     rsp, 30h
0x14005aebe  pop     rdi
0x14005aebf  retn
```
