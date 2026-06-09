# CH264FormatPlugin::CaptureCopyMemory(uchar *,ulong,uchar *,ulong,ulong,ulong,ulong *,ulong *,ulong *)

- ea: `0x140005730`
- end: `0x140005891`
- name: `?CaptureCopyMemory@CH264FormatPlugin@@UEAAJPEAEK0KKKPEAK11@Z`
- size: `353`
- prototype: `__int64 __fastcall(CH264FormatPlugin *this, unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int Size, unsigned int, unsigned int, unsigned int *, unsigned int *, unsigned int *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x140005730`
- `0x140040b40`

## pseudocode

```c
__int64 __fastcall CH264FormatPlugin::CaptureCopyMemory(
        CH264FormatPlugin *this,
        unsigned __int8 *a2,
        unsigned int a3,
        unsigned __int8 *a4,
        unsigned int Size,
        unsigned int a6,
        unsigned int a7,
        unsigned int *a8,
        unsigned int *a9,
        unsigned int *a10)
{
  __int64 v10; // rbx
  __int64 v14; // rcx
  unsigned int *v16; // r15
  unsigned int v17; // r9d
  unsigned int v18; // r12d
  unsigned int v19; // edx
  unsigned int v20; // r13d
  __int64 v21; // r11
  unsigned int v22; // ecx
  unsigned __int64 v23; // rdx
  unsigned int v24; // eax
  unsigned int v25; // [rsp+20h] [rbp-58h]
  unsigned int v26; // [rsp+A8h] [rbp+30h]

  v10 = a6;
  if ( a6 && a7 && a7 < a6 )
  {
    v16 = a10;
    v17 = 0;
    v18 = Size;
    *a10 = 0;
    while ( 1 )
    {
      v26 = v17;
      if ( !v18 )
        break;
      v19 = *a8 % a7;
      v20 = a7 - v19;
      v21 = v19;
      v22 = v10 - v19;
      if ( v18 < a7 - v19 )
      {
        v22 = v18;
        v20 = v18;
      }
      v23 = v10 * (*a8 / a7);
      v25 = v22;
      if ( v23 > 0xFFFFFFFF )
        goto LABEL_13;
      v24 = v23 + v21;
      if ( (int)v23 + (int)v21 < (unsigned int)v23 || v22 + v24 < v24 || v18 < v20 || v22 + v24 > a3 )
        goto LABEL_13;
      memmove(&a2[(unsigned int)v10 * (*a8 / a7) + v21], &a4[v17], v20);
      v18 -= v20;
      *a8 += v20;
      *a9 += v25;
      *a10 += v25;
      v17 = v20 + v26;
    }
  }
  else
  {
    v14 = *a9;
    if ( a3 < (unsigned int)v14 + Size )
    {
      v16 = a10;
LABEL_13:
      *v16 = 0;
    }
    else
    {
      memmove(&a2[v14], a4, Size);
      *a10 = Size;
      *a9 += Size;
      *a8 += Size;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x140005730  push    rbx
0x140005732  push    rbp
0x140005733  push    rsi
0x140005734  push    rdi
0x140005735  push    r12
0x140005737  push    r13
0x140005739  push    r14
0x14000573b  push    r15
0x14000573d  sub     rsp, 38h
0x140005741  mov     ebx, [rsp+78h+arg_28]
0x140005748  mov     rbp, r9
0x14000574b  mov     esi, r8d
0x14000574e  mov     r14, rdx
0x140005751  test    ebx, ebx
0x140005753  jnz     short loc_1400057A9
0x140005755  mov     rdi, [rsp+78h+arg_40]
0x14000575d  mov     ebx, dword ptr [rsp+78h+Size]
0x140005764  mov     ecx, [rdi]
0x140005766  lea     eax, [rcx+rbx]
0x140005769  cmp     esi, eax
0x14000576b  jb      loc_140005887
0x140005771  mov     r8d, ebx; Size
0x140005774  add     rcx, r14; void *
0x140005777  mov     rdx, rbp; Src
0x14000577a  call    memmove
0x14000577f  mov     rax, [rsp+78h+arg_48]
0x140005787  mov     [rax], ebx
0x140005789  mov     rax, [rsp+78h+arg_38]
0x140005791  add     [rdi], ebx
0x140005793  add     [rax], ebx
0x140005795  xor     eax, eax
0x140005797  add     rsp, 38h
0x14000579b  pop     r15
0x14000579d  pop     r14
0x14000579f  pop     r13
0x1400057a1  pop     r12
0x1400057a3  pop     rdi
0x1400057a4  pop     rsi
0x1400057a5  pop     rbp
0x1400057a6  pop     rbx
0x1400057a7  retn
0x1400057a9  mov     edi, [rsp+78h+arg_30]
0x1400057b0  test    edi, edi
0x1400057b2  jz      short loc_140005755
0x1400057b4  cmp     edi, ebx
0x1400057b6  jnb     short loc_140005755
0x1400057b8  mov     r15, [rsp+78h+arg_48]
0x1400057c0  xor     r9d, r9d
0x1400057c3  mov     r12d, dword ptr [rsp+78h+Size]
0x1400057cb  mov     [r15], r9d
0x1400057ce  mov     [rsp+78h+arg_28], r9d
0x1400057d6  mov     r8d, 0FFFFFFFFh
0x1400057dc  test    r12d, r12d
0x1400057df  jz      short loc_140005795
0x1400057e1  mov     rax, [rsp+78h+arg_38]
0x1400057e9  xor     edx, edx
0x1400057eb  mov     r13d, edi
0x1400057ee  mov     ecx, ebx
0x1400057f0  mov     eax, [rax]
0x1400057f2  div     edi
0x1400057f4  sub     r13d, edx
0x1400057f7  mov     r11d, edx
0x1400057fa  sub     ecx, edx
0x1400057fc  mov     r10d, eax
0x1400057ff  cmp     r12d, r13d
0x140005802  mov     edx, eax
0x140005804  cmovb   ecx, r12d
0x140005808  cmovb   r13d, r12d
0x14000580c  imul    rdx, rbx
0x140005810  mov     [rsp+78h+var_58], ecx
0x140005814  cmp     rdx, r8
0x140005817  ja      short loc_140005821
0x140005819  lea     eax, [rdx+r11]
0x14000581d  cmp     eax, edx
0x14000581f  jnb     short loc_14000582D
0x140005821  mov     dword ptr [r15], 0
0x140005828  jmp     loc_140005795
0x14000582d  lea     edx, [rcx+rax]
0x140005830  cmp     edx, eax
0x140005832  jb      short loc_140005821
0x140005834  cmp     r12d, r13d
0x140005837  jb      short loc_140005821
0x140005839  cmp     edx, esi
0x14000583b  ja      short loc_140005821
0x14000583d  imul    r10d, ebx
0x140005841  mov     edx, r9d
0x140005844  mov     r8d, r13d; Size
0x140005847  add     rdx, rbp; Src
0x14000584a  mov     ecx, r10d
0x14000584d  add     rcx, r14
0x140005850  add     rcx, r11; void *
0x140005853  call    memmove
0x140005858  mov     rax, [rsp+78h+arg_38]
0x140005860  sub     r12d, r13d
0x140005863  mov     rcx, [rsp+78h+arg_40]
0x14000586b  mov     r9d, [rsp+78h+arg_28]
0x140005873  add     [rax], r13d
0x140005876  mov     eax, [rsp+78h+var_58]
0x14000587a  add     [rcx], eax
0x14000587c  add     [r15], eax
0x14000587f  add     r9d, r13d
0x140005882  jmp     loc_1400057CE
0x140005887  mov     r15, [rsp+78h+arg_48]
0x14000588f  jmp     short loc_140005821
```
