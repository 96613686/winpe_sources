# SkmiCaptureLoadConfigIpValidationTables

- ea: `0x14006c84c`
- end: `0x14006cc0e`
- name: `SkmiCaptureLoadConfigIpValidationTables`
- size: `962`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14007c13c`

## callees

- `0x14000f0f0`
- `0x140037e68`
- `0x14006c84c`
- `0x1400d64a4`
- `0x1400dcf1c`

## pseudocode

```c
__int64 __fastcall SkmiCaptureLoadConfigIpValidationTables(__int64 a1, unsigned __int64 a2, __int64 a3, __int64 a4)
{
  int v5; // esi
  __int64 v6; // r13
  __int64 v7; // r12
  _OWORD *Pool; // rax
  int v9; // edx
  _OWORD *v10; // rdi
  int v11; // ebx
  __int64 v12; // rdx
  unsigned __int64 v14; // r15
  unsigned __int64 v15; // r14
  __int64 v16; // rbx
  unsigned int *v17; // rax
  unsigned int *v18; // rcx
  int v19; // edx
  char *v20; // r8
  __int64 v21; // r10
  __int64 v22; // r9
  unsigned int v23; // eax
  unsigned int v24; // esi
  unsigned __int64 v25; // rbx
  void *v26; // r15
  void *v27; // rax
  unsigned __int64 v28; // rbx
  void *v29; // r14
  void *v30; // rax
  __int64 v31; // [rsp+40h] [rbp-78h] BYREF
  __int64 v32; // [rsp+48h] [rbp-70h]
  _OWORD *v33; // [rsp+50h] [rbp-68h]
  unsigned __int64 v34; // [rsp+58h] [rbp-60h]
  __int64 v35; // [rsp+60h] [rbp-58h]
  __int64 v36; // [rsp+68h] [rbp-50h]
  _BYTE *v37; // [rsp+70h] [rbp-48h]
  unsigned __int64 v38; // [rsp+78h] [rbp-40h]

  v5 = a1;
  LODWORD(v31) = 0;
  v6 = 0;
  v35 = 0;
  v7 = 0;
  v32 = 0;
  Pool = (_OWORD *)SkAllocatePool(512, 0x20u);
  v10 = Pool;
  v33 = Pool;
  if ( !Pool )
    goto LABEL_2;
  v14 = 0;
  v15 = 0;
  v34 = 0;
  *Pool = 0;
  Pool[1] = 0;
  v16 = *(unsigned int *)(a3 + 80);
  v17 = (unsigned int *)RtlImageDirectoryEntryToData(v5, v9, 10, (int)&v31);
  v18 = v17;
  if ( v17 && (v19 = v31) != 0 )
  {
    v20 = (char *)v17 + (unsigned int)v31;
    if ( v20 > (char *)v17 )
    {
      v21 = (unsigned int)v16;
      v31 = v16;
      v22 = a1;
      if ( (unsigned __int64)v20 <= v16 + a1 )
      {
        v23 = *v17;
        if ( v19 == *v18 )
        {
          v36 = v16;
          if ( v23 >= 0x118 && (v18[36] & 0x400000) != 0 )
          {
            *((_WORD *)v10 + 14) |= 2u;
            v14 = *((_QWORD *)v18 + 33);
            v38 = v14;
            v6 = *((_QWORD *)v18 + 34);
            v35 = v6;
          }
          if ( *v18 >= 0xC0 && (v18[36] & 0x10000) != 0 )
          {
            *((_WORD *)v10 + 14) |= 4u;
            v15 = *((_QWORD *)v18 + 22);
            v34 = v15;
            v7 = *((_QWORD *)v18 + 23);
            v32 = v7;
          }
          v24 = (v18[36] >> 28) + 4;
          v37 = (char *)v10 + 28;
          if ( (*((_BYTE *)v10 + 28) & 2) != 0 && v6 )
          {
            if ( !v14 )
              goto LABEL_31;
            v25 = v6 * v24;
            if ( v25 >= 0xFFFFFFFF || v14 <= a2 || v25 + v14 <= v14 || v25 + v14 > v21 + a2 )
              goto LABEL_31;
            v26 = (void *)(a1 - a2 + v14);
            v27 = (void *)SkAllocatePool(512, v25);
            *(_QWORD *)v10 = v27;
            if ( !v27 )
              goto LABEL_2;
            v11 = RtlValidateAndCopyIpValidationTable(v26, v27);
            v22 = a1;
            v21 = v31;
            if ( v11 < 0 )
              goto LABEL_3;
            *((_DWORD *)v10 + 4) = v35;
          }
          if ( (*v37 & 4) == 0 || !v7 )
          {
LABEL_42:
            *((_DWORD *)v10 + 6) = v24;
            v11 = 0;
            goto LABEL_45;
          }
          if ( v15 )
          {
            v28 = v7 * v24;
            if ( v28 < 0xFFFFFFFF && v15 > a2 && v28 + v15 > v15 && v28 + v15 <= v21 + a2 )
            {
              v29 = (void *)(v22 - a2 + v15);
              v30 = (void *)SkAllocatePool(512, v7 * v24);
              *((_QWORD *)v10 + 1) = v30;
              if ( v30 )
              {
                v11 = RtlValidateAndCopyIpValidationTable(v29, v30);
                if ( v11 < 0 )
                  goto LABEL_3;
                *((_DWORD *)v10 + 5) = v7;
                goto LABEL_42;
              }
LABEL_2:
              v11 = -1073741670;
              goto LABEL_3;
            }
          }
LABEL_31:
          v11 = -1073741701;
          goto LABEL_3;
        }
      }
    }
    v11 = -1073741701;
  }
  else
  {
    v11 = 0;
  }
LABEL_45:
  if ( v11 >= 0 )
  {
    *((_WORD *)v10 + 14) |= 1u;
    *(_QWORD *)(a4 + 216) = v10;
    return (unsigned int)v11;
  }
LABEL_3:
  if ( v10 )
  {
    if ( *(_QWORD *)v10 )
      SkFreePool(512, *(_QWORD *)v10);
    v12 = *((_QWORD *)v10 + 1);
    if ( v12 )
      SkFreePool(512, v12);
    SkFreePool(512, v10);
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x14006c84c  mov     rax, rsp
0x14006c84f  mov     [rax+20h], r9
0x14006c853  mov     [rax+10h], rdx
0x14006c857  mov     [rax+8], rcx
0x14006c85b  push    rbx
0x14006c85c  push    rsi
0x14006c85d  push    rdi
0x14006c85e  push    r12
0x14006c860  push    r13
0x14006c862  push    r14
0x14006c864  push    r15
0x14006c866  sub     rsp, 80h
0x14006c86d  mov     rbx, r8
0x14006c870  mov     rsi, rcx
0x14006c873  mov     dword ptr [rax-78h], 0
0x14006c87a  mov     dword ptr [rax-80h], 0
0x14006c881  mov     dword ptr [rax-7Ch], 0
0x14006c888  xor     r13d, r13d
0x14006c88b  mov     [rax-58h], r13
0x14006c88f  xor     r12d, r12d
0x14006c892  mov     [rax-70h], r12
0x14006c896  lea     edx, [r13+20h]
0x14006c89a  mov     ecx, 200h
0x14006c89f  mov     r8d, 50496D4Dh
0x14006c8a5  call    SkAllocatePool
0x14006c8aa  mov     rdi, rax
0x14006c8ad  mov     [rsp+0B8h+var_68], rax
0x14006c8b2  test    rax, rax
0x14006c8b5  jnz     short loc_14006C909
0x14006c8b7  mov     ebx, 0C000009Ah
0x14006c8bc  test    rdi, rdi
0x14006c8bf  jz      short loc_14006C8F3
0x14006c8c1  mov     rdx, [rdi]
0x14006c8c4  test    rdx, rdx
0x14006c8c7  jz      short loc_14006C8D3
0x14006c8c9  mov     ecx, 200h
0x14006c8ce  call    SkFreePool
0x14006c8d3  mov     rdx, [rdi+8]
0x14006c8d7  test    rdx, rdx
0x14006c8da  jz      short loc_14006C8E6
0x14006c8dc  mov     ecx, 200h
0x14006c8e1  call    SkFreePool
0x14006c8e6  mov     rdx, rdi
0x14006c8e9  mov     ecx, 200h
0x14006c8ee  call    SkFreePool
0x14006c8f3  mov     eax, ebx
0x14006c8f5  add     rsp, 80h
0x14006c8fc  pop     r15
0x14006c8fe  pop     r14
0x14006c900  pop     r13
0x14006c902  pop     r12
0x14006c904  pop     rdi
0x14006c905  pop     rsi
0x14006c906  pop     rbx
0x14006c907  retn
0x14006c909  xor     r15d, r15d
0x14006c90c  xor     r14d, r14d
0x14006c90f  mov     [rsp+0B8h+var_60], r14
0x14006c914  xorps   xmm0, xmm0
0x14006c917  movups  xmmword ptr [rax], xmm0
0x14006c91a  movups  xmmword ptr [rax+10h], xmm0
0x14006c91e  mov     ebx, [rbx+50h]
0x14006c921  mov     [rsp+0B8h+var_84], ebx
0x14006c925  mov     [rsp+0B8h+var_7C], ebx
0x14006c929  lea     r8d, [r15+0Ah]
0x14006c92d  lea     r9, [rsp+0B8h+var_78]
0x14006c932  mov     rcx, rsi
0x14006c935  call    RtlImageDirectoryEntryToData
0x14006c93a  mov     rcx, rax
0x14006c93d  test    rax, rax
0x14006c940  jz      loc_14006CBDA
0x14006c946  mov     edx, dword ptr [rsp+0B8h+var_78]
0x14006c94a  test    edx, edx
0x14006c94c  jz      loc_14006CBDA
0x14006c952  lea     r8, [rax+rdx]
0x14006c956  cmp     r8, rax
0x14006c959  jbe     loc_14006CBCF
0x14006c95f  mov     r10d, ebx
0x14006c962  mov     [rsp+0B8h+var_78], rbx
0x14006c967  mov     r9, [rsp+0B8h+arg_0]
0x14006c96f  lea     rax, [rbx+r9]
0x14006c973  cmp     r8, rax
0x14006c976  ja      loc_14006CBCF
0x14006c97c  mov     eax, [rcx]
0x14006c97e  cmp     edx, eax
0x14006c980  jnz     loc_14006CBCF
0x14006c986  mov     [rsp+0B8h+var_50], rbx
0x14006c98b  cmp     eax, 118h
0x14006c990  jb      short loc_14006C9BB
0x14006c992  test    dword ptr [rcx+90h], 400000h
0x14006c99c  jz      short loc_14006C9BB
0x14006c99e  or      word ptr [rdi+1Ch], 2
0x14006c9a3  mov     r15, [rcx+108h]
0x14006c9aa  mov     [rsp+0B8h+var_40], r15
0x14006c9af  mov     r13, [rcx+110h]
0x14006c9b6  mov     [rsp+0B8h+var_58], r13
0x14006c9bb  cmp     dword ptr [rcx], 0C0h
0x14006c9c1  jb      short loc_14006C9F2
0x14006c9c3  test    dword ptr [rcx+90h], 10000h
0x14006c9cd  jz      short loc_14006C9F2
0x14006c9cf  mov     edx, 4
0x14006c9d4  or      [rdi+1Ch], dx
0x14006c9d8  mov     r14, [rcx+0B0h]
0x14006c9df  mov     [rsp+0B8h+var_60], r14
0x14006c9e4  mov     r12, [rcx+0B8h]
0x14006c9eb  mov     [rsp+0B8h+var_70], r12
0x14006c9f0  jmp     short loc_14006C9F7
0x14006c9f2  mov     edx, 4
0x14006c9f7  mov     esi, [rcx+90h]
0x14006c9fd  shr     esi, 1Ch
0x14006ca00  add     esi, edx
0x14006ca02  mov     [rsp+0B8h+var_80], esi
0x14006ca06  lea     rax, [rdi+1Ch]
0x14006ca0a  mov     [rsp+0B8h+var_48], rax
0x14006ca0f  test    byte ptr [rax], 2
0x14006ca12  jz      loc_14006CB18
0x14006ca18  test    r13, r13
0x14006ca1b  jz      loc_14006CB18
0x14006ca21  test    r15, r15
0x14006ca24  jz      loc_14006CB0E
0x14006ca2a  mov     ebx, esi
0x14006ca2c  imul    rbx, r13
0x14006ca30  mov     r13d, 0FFFFFFFFh
0x14006ca36  cmp     rbx, r13
0x14006ca39  jnb     loc_14006CB0E
0x14006ca3f  mov     rdx, [rsp+0B8h+arg_8]
0x14006ca47  cmp     r15, rdx
0x14006ca4a  jbe     loc_14006CB0E
0x14006ca50  lea     rcx, [rbx+r15]
0x14006ca54  cmp     rcx, r15
0x14006ca57  jbe     loc_14006CB0E
0x14006ca5d  lea     rax, [r10+rdx]
0x14006ca61  cmp     rcx, rax
0x14006ca64  ja      loc_14006CB0E
0x14006ca6a  mov     rax, r9
0x14006ca6d  sub     rax, rdx
0x14006ca70  add     r15, rax
0x14006ca73  mov     r8d, 50496D4Dh
0x14006ca79  mov     rdx, rbx
0x14006ca7c  mov     ecx, 200h
0x14006ca81  call    SkAllocatePool
0x14006ca86  mov     [rdi], rax
0x14006ca89  test    rax, rax
0x14006ca8c  jz      loc_14006C8B7
0x14006ca92  mov     [rsp+0B8h+var_98], rax; void *
0x14006ca97  mov     r9d, [rsp+0B8h+var_84]
0x14006ca9c  mov     r8, rbx
0x14006ca9f  mov     edx, esi
0x14006caa1  mov     rcx, r15; Src
0x14006caa4  call    RtlValidateAndCopyIpValidationTable
0x14006caa9  mov     ebx, eax
0x14006caab  mov     [rsp+0B8h+var_88], eax
0x14006caaf  mov     edx, 4
0x14006cab4  mov     r9, [rsp+0B8h+arg_0]
0x14006cabc  mov     r10, [rsp+0B8h+var_78]
0x14006cac1  jmp     short loc_14006CAFC
0x14006cac3  mov     ebx, eax
0x14006cac5  mov     [rsp+0B8h+var_88], eax
0x14006cac9  mov     edx, 4
0x14006cace  mov     r13d, 0FFFFFFFFh
0x14006cad4  mov     r9, [rsp+0B8h+arg_0]
0x14006cadc  mov     r12, [rsp+0B8h+var_70]
0x14006cae1  mov     r14, [rsp+0B8h+var_60]
0x14006cae6  mov     esi, [rsp+0B8h+var_80]
0x14006caea  mov     eax, [rsp+0B8h+var_7C]
0x14006caee  mov     [rsp+0B8h+var_84], eax
0x14006caf2  mov     rdi, [rsp+0B8h+var_68]
0x14006caf7  mov     r10, [rsp+0B8h+var_50]
0x14006cafc  test    ebx, ebx
0x14006cafe  js      loc_14006C8BC
0x14006cb04  mov     rax, [rsp+0B8h+var_58]
0x14006cb09  mov     [rdi+10h], eax
0x14006cb0c  jmp     short loc_14006CB1E
0x14006cb0e  mov     ebx, 0C000007Bh
0x14006cb13  jmp     loc_14006C8BC
0x14006cb18  mov     r13d, 0FFFFFFFFh
0x14006cb1e  mov     rax, [rsp+0B8h+var_48]
0x14006cb23  test    [rax], dl
0x14006cb25  jz      loc_14006CBC8
0x14006cb2b  test    r12, r12
0x14006cb2e  jz      loc_14006CBC8
0x14006cb34  test    r14, r14
0x14006cb37  jz      short loc_14006CB0E
0x14006cb39  mov     ebx, esi
0x14006cb3b  imul    rbx, r12
0x14006cb3f  cmp     rbx, r13
0x14006cb42  jnb     short loc_14006CB0E
0x14006cb44  mov     rdx, [rsp+0B8h+arg_8]
0x14006cb4c  cmp     r14, rdx
0x14006cb4f  jbe     short loc_14006CB0E
0x14006cb51  lea     rcx, [rbx+r14]
0x14006cb55  cmp     rcx, r14
0x14006cb58  jbe     short loc_14006CB0E
0x14006cb5a  lea     rax, [r10+rdx]
0x14006cb5e  cmp     rcx, rax
0x14006cb61  ja      short loc_14006CB0E
0x14006cb63  sub     r9, rdx
0x14006cb66  add     r14, r9
0x14006cb69  mov     r8d, 50496D4Dh
0x14006cb6f  mov     rdx, rbx
0x14006cb72  mov     ecx, 200h
0x14006cb77  call    SkAllocatePool
0x14006cb7c  mov     [rdi+8], rax
0x14006cb80  test    rax, rax
0x14006cb83  jz      loc_14006C8B7
0x14006cb89  mov     [rsp+0B8h+var_98], rax; void *
0x14006cb8e  mov     r9d, [rsp+0B8h+var_84]
0x14006cb93  mov     r8, rbx
0x14006cb96  mov     edx, esi
0x14006cb98  mov     rcx, r14; Src
0x14006cb9b  call    RtlValidateAndCopyIpValidationTable
0x14006cba0  mov     ebx, eax
0x14006cba2  mov     [rsp+0B8h+var_88], eax
0x14006cba6  jmp     short loc_14006CBBC
0x14006cba8  mov     ebx, eax
0x14006cbaa  mov     [rsp+0B8h+var_88], eax
0x14006cbae  mov     r12, [rsp+0B8h+var_70]
0x14006cbb3  mov     esi, [rsp+0B8h+var_80]
0x14006cbb7  mov     rdi, [rsp+0B8h+var_68]
0x14006cbbc  test    ebx, ebx
0x14006cbbe  js      loc_14006C8BC
0x14006cbc4  mov     [rdi+14h], r12d
0x14006cbc8  mov     [rdi+18h], esi
0x14006cbcb  xor     ebx, ebx
0x14006cbcd  jmp     short loc_14006CBED
0x14006cbcf  mov     ebx, 0C000007Bh
0x14006cbd4  mov     [rsp+0B8h+var_88], ebx
0x14006cbd8  jmp     short loc_14006CBED
0x14006cbda  xor     ebx, ebx
0x14006cbdc  mov     [rsp+0B8h+var_88], ebx
0x14006cbe0  jmp     short loc_14006CBED
0x14006cbe2  mov     ebx, eax
0x14006cbe4  mov     [rsp+0B8h+var_88], eax
0x14006cbe8  mov     rdi, [rsp+0B8h+var_68]
0x14006cbed  test    ebx, ebx
0x14006cbef  js      loc_14006C8BC
0x14006cbf5  or      word ptr [rdi+1Ch], 1
0x14006cbfa  mov     rax, [rsp+0B8h+arg_18]
0x14006cc02  mov     [rax+0D8h], rdi
0x14006cc09  jmp     loc_14006C8F3
```
