# CheckType(_AMMediaType const *,_GUID const * const *,uint)

- ea: `0x180003570`
- end: `0x180003659`
- name: `?CheckType@@YAJPEBU_AMMediaType@@PEBQEBU_GUID@@I@Z`
- size: `233`
- prototype: `__int64 __fastcall(const struct _AMMediaType *, const struct _GUID *const *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180008680`
- `0x1800089b0`

## callees

- `0x180003570`

## pseudocode

```c
__int64 __fastcall CheckType(const struct _AMMediaType *a1, const struct _GUID *const *a2)
{
  __int64 v2; // rdx
  GUID *v3; // r8

  if ( *(_QWORD *)&a1->majortype.Data1 != *(_QWORD *)&MEDIATYPE_Video.Data1
    || *(_QWORD *)a1->majortype.Data4 != *(_QWORD *)MEDIATYPE_Video.Data4
    || (*(_QWORD *)&a1->formattype.Data1 != *(_QWORD *)&FORMAT_VideoInfo.Data1
     || *(_QWORD *)a1->formattype.Data4 != *(_QWORD *)FORMAT_VideoInfo.Data4)
    && (*(_QWORD *)&a1->formattype.Data1 != *(_QWORD *)&FORMAT_VideoInfo2.Data1
     || *(_QWORD *)a1->formattype.Data4 != *(_QWORD *)FORMAT_VideoInfo2.Data4)
    && (*(_QWORD *)&a1->formattype.Data1 != *(_QWORD *)&FORMAT_MFVideoFormat.Data1
     || *(_QWORD *)a1->formattype.Data4 != *(_QWORD *)FORMAT_MFVideoFormat.Data4)
    || *(_QWORD *)&a1->formattype.Data1 == *(_QWORD *)&FORMAT_VideoInfo.Data1
    && *(_QWORD *)a1->formattype.Data4 == *(_QWORD *)FORMAT_VideoInfo.Data4
    && a1->cbFormat < 0x58
    || *(_QWORD *)&a1->formattype.Data1 == *(_QWORD *)&FORMAT_VideoInfo2.Data1
    && *(_QWORD *)a1->formattype.Data4 == *(_QWORD *)FORMAT_VideoInfo2.Data4
    && a1->cbFormat < 0x70
    || *(_QWORD *)&a1->formattype.Data1 == *(_QWORD *)&FORMAT_MFVideoFormat.Data1
    && *(_QWORD *)a1->formattype.Data4 == *(_QWORD *)FORMAT_MFVideoFormat.Data4
    && a1->cbFormat < 0xB0
    || !a1->pbFormat )
  {
    return 2147746309LL;
  }
  v2 = 0;
  while ( 1 )
  {
    v3 = off_18001B010[v2];
    if ( *(_QWORD *)&v3->Data1 == *(_QWORD *)&a1->subtype.Data1 && *(_QWORD *)v3->Data4 == *(_QWORD *)a1->subtype.Data4 )
      break;
    v2 = (unsigned int)(v2 + 1);
    if ( (unsigned int)v2 >= 0xC )
    {
      if ( (_DWORD)v2 == 12 )
        return 2147746309LL;
      return 0;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180003570  mov     rax, [rcx]
0x180003573  cmp     rax, qword ptr cs:MEDIATYPE_Video.Data1
0x18000357a  jnz     loc_180003653
0x180003580  mov     rax, [rcx+8]
0x180003584  cmp     rax, qword ptr cs:MEDIATYPE_Video.Data4
0x18000358b  jnz     loc_180003653
0x180003591  mov     rdx, qword ptr cs:FORMAT_VideoInfo.Data1
0x180003598  mov     r8, qword ptr cs:FORMAT_MFVideoFormat.Data4
0x18000359f  mov     r11, qword ptr cs:FORMAT_MFVideoFormat.Data1
0x1800035a6  mov     r10, qword ptr cs:FORMAT_VideoInfo2.Data4
0x1800035ad  mov     r9, qword ptr cs:FORMAT_VideoInfo2.Data1
0x1800035b4  mov     rax, qword ptr cs:FORMAT_VideoInfo.Data4
0x1800035bb  cmp     [rcx+2Ch], rdx
0x1800035bf  jnz     short loc_1800035C7
0x1800035c1  cmp     [rcx+34h], rax
0x1800035c5  jz      short loc_1800035DF
0x1800035c7  cmp     [rcx+2Ch], r9
0x1800035cb  jnz     short loc_1800035D3
0x1800035cd  cmp     [rcx+34h], r10
0x1800035d1  jz      short loc_1800035DF
0x1800035d3  cmp     [rcx+2Ch], r11
0x1800035d7  jnz     short loc_180003653
0x1800035d9  cmp     [rcx+34h], r8
0x1800035dd  jnz     short loc_180003653
0x1800035df  cmp     [rcx+2Ch], rdx
0x1800035e3  jnz     short loc_1800035F1
0x1800035e5  cmp     [rcx+34h], rax
0x1800035e9  jnz     short loc_1800035F1
0x1800035eb  cmp     dword ptr [rcx+48h], 58h ; 'X'
0x1800035ef  jb      short loc_180003653
0x1800035f1  cmp     [rcx+2Ch], r9
0x1800035f5  jnz     short loc_180003603
0x1800035f7  cmp     [rcx+34h], r10
0x1800035fb  jnz     short loc_180003603
0x1800035fd  cmp     dword ptr [rcx+48h], 70h ; 'p'
0x180003601  jb      short loc_180003653
0x180003603  cmp     [rcx+2Ch], r11
0x180003607  jnz     short loc_180003618
0x180003609  cmp     [rcx+34h], r8
0x18000360d  jnz     short loc_180003618
0x18000360f  cmp     dword ptr [rcx+48h], 0B0h
0x180003616  jb      short loc_180003653
0x180003618  cmp     qword ptr [rcx+50h], 0
0x18000361d  jz      short loc_180003653
0x18000361f  xor     edx, edx
0x180003621  lea     r9, off_18001B010
0x180003628  nop     dword ptr [rax+rax+00000000h]
0x180003630  mov     r8, [r9+rdx*8]
0x180003634  mov     rax, [r8]
0x180003637  cmp     rax, [rcx+10h]
0x18000363b  jnz     short loc_180003647
0x18000363d  mov     rax, [r8+8]
0x180003641  cmp     rax, [rcx+18h]
0x180003645  jz      short loc_180003650
0x180003647  inc     edx
0x180003649  cmp     edx, 0Ch
0x18000364c  jb      short loc_180003630
0x18000364e  jz      short loc_180003653
0x180003650  xor     eax, eax
0x180003652  retn
0x180003653  mov     eax, 80040205h
0x180003658  retn
```
