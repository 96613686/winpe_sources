# BitmapSize(_AMMediaType *)

- ea: `0x180003210`
- end: `0x1800032e2`
- name: `?BitmapSize@@YAKPEAU_AMMediaType@@@Z`
- size: `210`
- prototype: `__int64 __fastcall(struct _AMMediaType *)`
- caller_count: `4`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180002db0`
- `0x180004540`
- `0x180004a20`
- `0x180007e90`

## callees

- `0x180001968`
- `0x1800019b4`
- `0x180003210`
- `0x180003950`
- `0x180004f30`

## pseudocode

```c
__int64 __fastcall BitmapSize(struct _AMMediaType *a1)
{
  unsigned int v2; // esi
  struct tagVIDEOINFOHEADER *v3; // rax
  struct tagVIDEOINFOHEADER *v4; // rdi
  unsigned __int64 v5; // rdx

  if ( *(_QWORD *)&FORMAT_MFVideoFormat.Data1 == *(_QWORD *)&a1->formattype.Data1
    && *(_QWORD *)FORMAT_MFVideoFormat.Data4 == *(_QWORD *)a1->formattype.Data4 )
  {
    v2 = 0;
    v3 = (struct tagVIDEOINFOHEADER *)operator new[](0x458u);
    v4 = v3;
    if ( v3 )
    {
      ConvertMFVideoFormatToVIH3(v3, (struct _MFVIDEOFORMAT *)a1->pbFormat);
      v2 = ImageSize(&v4->bmiHeader);
      operator delete(v4, v5);
    }
    return v2;
  }
  else if ( *(_QWORD *)&FORMAT_VideoInfo.Data1 == *(_QWORD *)&a1->formattype.Data1
         && *(_QWORD *)FORMAT_VideoInfo.Data4 == *(_QWORD *)a1->formattype.Data4 )
  {
    return ImageSize((const struct tagBITMAPINFOHEADER *)(a1->pbFormat + 48));
  }
  else if ( *(_QWORD *)&FORMAT_VideoInfo2.Data1 == *(_QWORD *)&a1->formattype.Data1
         && *(_QWORD *)FORMAT_VideoInfo2.Data4 == *(_QWORD *)a1->formattype.Data4 )
  {
    return ImageSize((const struct tagBITMAPINFOHEADER *)(a1->pbFormat + 72));
  }
  else
  {
    return 0;
  }
}

```

## disassembly

```asm
0x180003210  push    rbx
0x180003212  sub     rsp, 20h
0x180003216  mov     rax, qword ptr cs:FORMAT_MFVideoFormat.Data1
0x18000321d  mov     rbx, rcx
0x180003220  cmp     rax, [rcx+2Ch]
0x180003224  jnz     short loc_180003282
0x180003226  mov     rax, qword ptr cs:FORMAT_MFVideoFormat.Data4
0x18000322d  cmp     rax, [rcx+34h]
0x180003231  jnz     short loc_180003282
0x180003233  mov     [rsp+28h+arg_0], rsi
0x180003238  mov     ecx, 458h; unsigned __int64
0x18000323d  mov     [rsp+28h+arg_8], rdi
0x180003242  xor     esi, esi
0x180003244  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180003249  mov     rdi, rax
0x18000324c  test    rax, rax
0x18000324f  jz      short loc_180003270
0x180003251  mov     rdx, [rbx+50h]; struct _MFVIDEOFORMAT *
0x180003255  mov     rcx, rax; struct tagVIDEOINFOHEADER *
0x180003258  call    ?ConvertMFVideoFormatToVIH3@@YAJPEAUtagVIDEOINFOHEADER@@PEAU_MFVIDEOFORMAT@@@Z; ConvertMFVideoFormatToVIH3(tagVIDEOINFOHEADER *,_MFVIDEOFORMAT *)
0x18000325d  lea     rcx, [rdi+30h]; struct tagBITMAPINFOHEADER *
0x180003261  call    ?ImageSize@@YAKPEBUtagBITMAPINFOHEADER@@@Z; ImageSize(tagBITMAPINFOHEADER const *)
0x180003266  mov     rcx, rdi; void *
0x180003269  mov     esi, eax
0x18000326b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180003270  mov     rdi, [rsp+28h+arg_8]
0x180003275  mov     eax, esi
0x180003277  mov     rsi, [rsp+28h+arg_0]
0x18000327c  add     rsp, 20h
0x180003280  pop     rbx
0x180003281  retn
0x180003282  mov     rax, qword ptr cs:FORMAT_VideoInfo.Data1
0x180003289  cmp     rax, [rcx+2Ch]
0x18000328d  jnz     short loc_1800032AE
0x18000328f  mov     rax, qword ptr cs:FORMAT_VideoInfo.Data4
0x180003296  cmp     rax, [rcx+34h]
0x18000329a  jnz     short loc_1800032AE
0x18000329c  mov     rcx, [rcx+50h]
0x1800032a0  add     rcx, 30h ; '0'; struct tagBITMAPINFOHEADER *
0x1800032a4  add     rsp, 20h
0x1800032a8  pop     rbx
0x1800032a9  jmp     ?ImageSize@@YAKPEBUtagBITMAPINFOHEADER@@@Z; ImageSize(tagBITMAPINFOHEADER const *)
0x1800032ae  mov     rax, qword ptr cs:FORMAT_VideoInfo2.Data1
0x1800032b5  cmp     rax, [rcx+2Ch]
0x1800032b9  jnz     short loc_1800032DA
0x1800032bb  mov     rax, qword ptr cs:FORMAT_VideoInfo2.Data4
0x1800032c2  cmp     rax, [rcx+34h]
0x1800032c6  jnz     short loc_1800032DA
0x1800032c8  mov     rcx, [rcx+50h]
0x1800032cc  add     rcx, 48h ; 'H'; struct tagBITMAPINFOHEADER *
0x1800032d0  add     rsp, 20h
0x1800032d4  pop     rbx
0x1800032d5  jmp     ?ImageSize@@YAKPEBUtagBITMAPINFOHEADER@@@Z; ImageSize(tagBITMAPINFOHEADER const *)
0x1800032da  xor     eax, eax
0x1800032dc  add     rsp, 20h
0x1800032e0  pop     rbx
0x1800032e1  retn
```
