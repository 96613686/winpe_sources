# CMPEG2TSFormatPlugin::DataIntersect(KSDATAFORMAT *,KSDATAFORMAT *,ulong,void *,ulong *)

- ea: `0x14003e760`
- end: `0x14003e903`
- name: `?DataIntersect@CMPEG2TSFormatPlugin@@UEAAJPEATKSDATAFORMAT@@0KPEAXPEAK@Z`
- size: `419`
- prototype: `int(CMPEG2TSFormatPlugin *__hidden this, union KSDATAFORMAT *, union KSDATAFORMAT *, unsigned int, void *, unsigned int *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x140004bac`
- `0x14003e760`
- `0x140040b40`

## pseudocode

```c
__int64 __fastcall CMPEG2TSFormatPlugin::DataIntersect(
        CMPEG2TSFormatPlugin *this,
        union KSDATAFORMAT *a2,
        union KSDATAFORMAT *a3,
        unsigned int a4,
        void *a5,
        unsigned int *a6)
{
  LONGLONG v6; // rax
  LONGLONG *v7; // rcx
  LONGLONG v8; // rax
  PDEVICE_OBJECT v10; // rcx
  __int64 v11; // rdx
  LONGLONG v12; // rax
  LONGLONG v13; // rax

  v6 = *(&a2->Alignment + 4) - *(_QWORD *)&GUID_138aa9a4_1ee2_4c5b_988e_19abfdbc8a11.Data1;
  if ( !v6 )
    v6 = *(&a2->Alignment + 5) - *(_QWORD *)GUID_138aa9a4_1ee2_4c5b_988e_19abfdbc8a11.Data4;
  v7 = &a3->Alignment + 4;
  if ( !v6 )
  {
    v8 = *v7 - *(_QWORD *)&GUID_138aa9a4_1ee2_4c5b_988e_19abfdbc8a11.Data1;
    if ( *v7 == *(_QWORD *)&GUID_138aa9a4_1ee2_4c5b_988e_19abfdbc8a11.Data1 )
      v8 = *(&a3->Alignment + 5) - *(_QWORD *)GUID_138aa9a4_1ee2_4c5b_988e_19abfdbc8a11.Data4;
    if ( !v8 && a2->FormatSize >= 0x50 )
    {
      if ( !a4 )
      {
        *a6 = 80;
        return 2147483653LL;
      }
      if ( a4 >= 0x50 )
      {
        if ( a2->SampleSize == a3->SampleSize )
        {
          if ( a3->FormatSize != 80 )
          {
            v10 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 5u )
              return 3221226098LL;
            v11 = 10;
            goto LABEL_39;
          }
          if ( a2[1].FormatSize != 4 || a2[1].Flags != 188 || a2[1].SampleSize != 192 )
            return 3221225485LL;
          *a6 = 80;
          goto LABEL_21;
        }
        return 3221226098LL;
      }
      return 3221225507LL;
    }
  }
  v12 = *(&a2->Alignment + 4) - *(_QWORD *)&GUID_e06d8023_db46_11cf_b4d1_00805f6cbbea.Data1;
  if ( !v12 )
    v12 = *(&a2->Alignment + 5) - *(_QWORD *)GUID_e06d8023_db46_11cf_b4d1_00805f6cbbea.Data4;
  if ( v12 )
    return 3221226098LL;
  v13 = *v7 - *(_QWORD *)&GUID_e06d8023_db46_11cf_b4d1_00805f6cbbea.Data1;
  if ( *v7 == *(_QWORD *)&GUID_e06d8023_db46_11cf_b4d1_00805f6cbbea.Data1 )
    v13 = *(&a3->Alignment + 5) - *(_QWORD *)GUID_e06d8023_db46_11cf_b4d1_00805f6cbbea.Data4;
  if ( v13 || a2->FormatSize < 0x40 )
    return 3221226098LL;
  if ( !a4 )
  {
    *a6 = 64;
    return 2147483653LL;
  }
  if ( a4 < 0x40 )
    return 3221225507LL;
  if ( a2->SampleSize == a3->SampleSize )
  {
    if ( a3->FormatSize != 64 )
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 5u )
        return 3221226098LL;
      v11 = 11;
LABEL_39:
      WPP_SF_(v10->AttachedDevice, v11, WPP_76389ff8e0f43d9eb559368648028ddd_Traceguids);
      return 3221226098LL;
    }
    *a6 = 64;
LABEL_21:
    memmove(a5, a3, a3->FormatSize);
    return 0;
  }
  return 3221226098LL;
}

```

## disassembly

```asm
0x14003e760  sub     rsp, 28h
0x14003e764  mov     rax, [rdx+20h]
0x14003e768  mov     r10, r8
0x14003e76b  mov     r11, qword ptr cs:_GUID_138aa9a4_1ee2_4c5b_988e_19abfdbc8a11.Data1
0x14003e772  mov     r8, qword ptr cs:_GUID_138aa9a4_1ee2_4c5b_988e_19abfdbc8a11.Data4
0x14003e779  sub     rax, r11
0x14003e77c  jnz     short loc_14003E785
0x14003e77e  mov     rax, [rdx+28h]
0x14003e782  sub     rax, r8
0x14003e785  lea     rcx, [r10+20h]
0x14003e789  test    rax, rax
0x14003e78c  jnz     loc_14003E855
0x14003e792  mov     rax, [rcx]
0x14003e795  sub     rax, r11
0x14003e798  jnz     short loc_14003E7A1
0x14003e79a  mov     rax, [rcx+8]
0x14003e79e  sub     rax, r8
0x14003e7a1  test    rax, rax
0x14003e7a4  jnz     loc_14003E855
0x14003e7aa  lea     r8d, [rax+50h]
0x14003e7ae  cmp     [rdx], r8d
0x14003e7b1  jb      loc_14003E855
0x14003e7b7  test    r9d, r9d
0x14003e7ba  jnz     short loc_14003E7CE
0x14003e7bc  mov     rax, [rsp+28h+arg_28]
0x14003e7c1  mov     [rax], r8d
0x14003e7c4  mov     eax, 80000005h
0x14003e7c9  jmp     loc_14003E8F1
0x14003e7ce  cmp     r9d, r8d
0x14003e7d1  jb      loc_14003E8A9
0x14003e7d7  mov     eax, [r10+8]
0x14003e7db  cmp     [rdx+8], eax
0x14003e7de  jnz     loc_14003E8EC
0x14003e7e4  cmp     [r10], r8d
0x14003e7e7  jz      short loc_14003E814
0x14003e7e9  mov     rcx, cs:WPP_GLOBAL_Control
0x14003e7f0  lea     rax, WPP_GLOBAL_Control
0x14003e7f7  cmp     rcx, rax
0x14003e7fa  jz      loc_14003E8EC
0x14003e800  cmp     byte ptr [rcx+29h], 5
0x14003e804  jb      loc_14003E8EC
0x14003e80a  mov     edx, 0Ah
0x14003e80f  jmp     loc_14003E8DC
0x14003e814  cmp     dword ptr [rdx+40h], 4
0x14003e818  jnz     short loc_14003E84B
0x14003e81a  cmp     dword ptr [rdx+44h], 0BCh
0x14003e821  jnz     short loc_14003E84B
0x14003e823  cmp     dword ptr [rdx+48h], 0C0h
0x14003e82a  jnz     short loc_14003E84B
0x14003e82c  mov     rax, [rsp+28h+arg_28]
0x14003e831  mov     [rax], r8d
0x14003e834  mov     r8d, [r10]; Size
0x14003e837  mov     rdx, r10; Src
0x14003e83a  mov     rcx, [rsp+28h+arg_20]; void *
0x14003e83f  call    memmove
0x14003e844  xor     eax, eax
0x14003e846  jmp     loc_14003E8F1
0x14003e84b  mov     eax, 0C000000Dh
0x14003e850  jmp     loc_14003E8F1
0x14003e855  mov     rax, [rdx+20h]
0x14003e859  mov     r11, qword ptr cs:_GUID_e06d8023_db46_11cf_b4d1_00805f6cbbea.Data1
0x14003e860  mov     r8, qword ptr cs:_GUID_e06d8023_db46_11cf_b4d1_00805f6cbbea.Data4
0x14003e867  sub     rax, r11
0x14003e86a  jnz     short loc_14003E873
0x14003e86c  mov     rax, [rdx+28h]
0x14003e870  sub     rax, r8
0x14003e873  test    rax, rax
0x14003e876  jnz     short loc_14003E8EC
0x14003e878  mov     rax, [rcx]
0x14003e87b  sub     rax, r11
0x14003e87e  jnz     short loc_14003E887
0x14003e880  mov     rax, [rcx+8]
0x14003e884  sub     rax, r8
0x14003e887  test    rax, rax
0x14003e88a  jnz     short loc_14003E8EC
0x14003e88c  lea     ecx, [rax+40h]
0x14003e88f  cmp     [rdx], ecx
0x14003e891  jb      short loc_14003E8EC
0x14003e893  test    r9d, r9d
0x14003e896  jnz     short loc_14003E8A4
0x14003e898  mov     rax, [rsp+28h+arg_28]
0x14003e89d  mov     [rax], ecx
0x14003e89f  jmp     loc_14003E7C4
0x14003e8a4  cmp     r9d, ecx
0x14003e8a7  jnb     short loc_14003E8B0
0x14003e8a9  mov     eax, 0C0000023h
0x14003e8ae  jmp     short loc_14003E8F1
0x14003e8b0  mov     eax, [r10+8]
0x14003e8b4  cmp     [rdx+8], eax
0x14003e8b7  jnz     short loc_14003E8EC
0x14003e8b9  cmp     [r10], ecx
0x14003e8bc  jz      short loc_14003E8F7
0x14003e8be  mov     rcx, cs:WPP_GLOBAL_Control
0x14003e8c5  lea     rax, WPP_GLOBAL_Control
0x14003e8cc  cmp     rcx, rax
0x14003e8cf  jz      short loc_14003E8EC
0x14003e8d1  cmp     byte ptr [rcx+29h], 5
0x14003e8d5  jb      short loc_14003E8EC
0x14003e8d7  mov     edx, 0Bh
0x14003e8dc  mov     rcx, [rcx+18h]
0x14003e8e0  lea     r8, WPP_76389ff8e0f43d9eb559368648028ddd_Traceguids
0x14003e8e7  call    WPP_SF_
0x14003e8ec  mov     eax, 0C0000272h
0x14003e8f1  add     rsp, 28h
0x14003e8f5  retn
0x14003e8f7  mov     rax, [rsp+28h+arg_28]
0x14003e8fc  mov     [rax], ecx
0x14003e8fe  jmp     loc_14003E834
```
