# CStreamFormatPlugin::DataIntersect(KSDATAFORMAT *,KSDATAFORMAT *,ulong,void *,ulong *)

- ea: `0x14003d760`
- end: `0x14003d871`
- name: `?DataIntersect@CStreamFormatPlugin@@UEAAJPEATKSDATAFORMAT@@0KPEAXPEAK@Z`
- size: `273`
- prototype: `int(CStreamFormatPlugin *__hidden this, union KSDATAFORMAT *, union KSDATAFORMAT *, unsigned int, void *, unsigned int *)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x14003d760`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x14003d7bb`
- `ntoskrnl!RtlCompareMemory` at `0x14003d7bb`

## pseudocode

```c
__int64 __fastcall CStreamFormatPlugin::DataIntersect(
        CStreamFormatPlugin *this,
        union KSDATAFORMAT *a2,
        union KSDATAFORMAT *a3,
        unsigned int a4,
        _OWORD *a5,
        unsigned int *a6)
{
  unsigned int v7; // edx

  if ( a4 )
  {
    if ( a4 >= 0xB0 )
    {
      if ( a2->FormatSize == 320 && a3->FormatSize == 320 && RtlCompareMemory(a2, a3, 0x40u) == 64 )
      {
        v7 = 0;
        *a5 = *(_OWORD *)&a3->FormatSize;
        a5[1] = *((_OWORD *)&a3->Alignment + 1);
        a5[2] = *((_OWORD *)&a3->Alignment + 2);
        a5[3] = *((_OWORD *)&a3->Alignment + 3);
        *(_DWORD *)a5 = 176;
        a5[4] = *((_OWORD *)&a3[3].Alignment + 1);
        a5[5] = *((_OWORD *)&a3[3].Alignment + 2);
        a5[6] = *((_OWORD *)&a3[3].Alignment + 3);
        a5[7] = *(_OWORD *)&a3[4].FormatSize;
        a5[8] = *((_OWORD *)&a3[4].Alignment + 1);
        a5[9] = *((_OWORD *)&a3[4].Alignment + 2);
        a5[10] = *((_OWORD *)&a3[4].Alignment + 3);
        *a6 = 176;
        *a6 = *(_DWORD *)a5;
      }
      else
      {
        return (unsigned int)-1073741811;
      }
    }
    else
    {
      return (unsigned int)-1073741789;
    }
  }
  else
  {
    v7 = -2147483643;
    *a6 = 176;
  }
  return v7;
}

```

## disassembly

```asm
0x14003d760  push    rbx
0x14003d762  sub     rsp, 20h
0x14003d766  mov     rbx, r8
0x14003d769  mov     rax, rdx
0x14003d76c  test    r9d, r9d
0x14003d76f  jnz     short loc_14003D786
0x14003d771  mov     rax, [rsp+28h+arg_28]
0x14003d776  mov     edx, 80000005h
0x14003d77b  mov     dword ptr [rax], 0B0h
0x14003d781  jmp     loc_14003D868
0x14003d786  cmp     r9d, 0B0h
0x14003d78d  jnb     short loc_14003D799
0x14003d78f  mov     edx, 0C0000023h
0x14003d794  jmp     loc_14003D868
0x14003d799  mov     ecx, 140h
0x14003d79e  cmp     [rdx], ecx
0x14003d7a0  jnz     loc_14003D863
0x14003d7a6  cmp     [r8], ecx
0x14003d7a9  jnz     loc_14003D863
0x14003d7af  mov     r8d, 40h ; '@'; Length
0x14003d7b5  mov     rdx, rbx; Source2
0x14003d7b8  mov     rcx, rax; Source1
0x14003d7bb  call    cs:__imp_RtlCompareMemory
0x14003d7c2  nop     dword ptr [rax+rax+00h]
0x14003d7c7  cmp     rax, 40h ; '@'
0x14003d7cb  jnz     loc_14003D863
0x14003d7d1  movups  xmm0, xmmword ptr [rbx]
0x14003d7d4  mov     rax, [rsp+28h+arg_20]
0x14003d7d9  xor     edx, edx
0x14003d7db  mov     rcx, [rsp+28h+arg_28]
0x14003d7e0  movups  xmmword ptr [rax], xmm0
0x14003d7e3  movups  xmm1, xmmword ptr [rbx+10h]
0x14003d7e7  movups  xmmword ptr [rax+10h], xmm1
0x14003d7eb  movups  xmm0, xmmword ptr [rbx+20h]
0x14003d7ef  movups  xmmword ptr [rax+20h], xmm0
0x14003d7f3  movups  xmm1, xmmword ptr [rbx+30h]
0x14003d7f7  movups  xmmword ptr [rax+30h], xmm1
0x14003d7fb  mov     dword ptr [rax], 0B0h
0x14003d801  movups  xmm0, xmmword ptr [rbx+0D0h]
0x14003d808  movups  xmmword ptr [rax+40h], xmm0
0x14003d80c  movups  xmm1, xmmword ptr [rbx+0E0h]
0x14003d813  movups  xmmword ptr [rax+50h], xmm1
0x14003d817  movups  xmm0, xmmword ptr [rbx+0F0h]
0x14003d81e  movups  xmmword ptr [rax+60h], xmm0
0x14003d822  movups  xmm1, xmmword ptr [rbx+100h]
0x14003d829  movups  xmmword ptr [rax+70h], xmm1
0x14003d82d  movups  xmm0, xmmword ptr [rbx+110h]
0x14003d834  movups  xmmword ptr [rax+80h], xmm0
0x14003d83b  movups  xmm1, xmmword ptr [rbx+120h]
0x14003d842  movups  xmmword ptr [rax+90h], xmm1
0x14003d849  movups  xmm0, xmmword ptr [rbx+130h]
0x14003d850  movups  xmmword ptr [rax+0A0h], xmm0
0x14003d857  mov     dword ptr [rcx], 0B0h
0x14003d85d  mov     eax, [rax]
0x14003d85f  mov     [rcx], eax
0x14003d861  jmp     short loc_14003D868
0x14003d863  mov     edx, 0C000000Dh
0x14003d868  mov     eax, edx
0x14003d86a  add     rsp, 20h
0x14003d86e  pop     rbx
0x14003d86f  retn
```
