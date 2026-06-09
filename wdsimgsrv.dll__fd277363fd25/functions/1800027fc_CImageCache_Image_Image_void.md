# CImageCache::Image::~Image(void)

- ea: `0x1800027fc`
- end: `0x180002872`
- name: `??1Image@CImageCache@@QEAA@XZ`
- size: `118`
- prototype: `void __fastcall(CImageCache::Image *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180002878`

## callees

- `0x1800027fc`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x18000280d`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180002826`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180002840`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000280d`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180002826`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180002840`
- `WdsImage!WdsImgClose` at `0x18000285a`
- `WdsImage!WdsImgClose` at `0x18000285a`

## pseudocode

```c
void __fastcall CImageCache::Image::~Image(CImageCache::Image *this)
{
  void *v2; // rcx
  void *v3; // rcx
  void *v4; // rcx

  v2 = *(void **)this;
  if ( v2 )
  {
    operator delete[](v2);
    *(_QWORD *)this = 0;
  }
  v3 = (void *)*((_QWORD *)this + 2);
  if ( v3 )
  {
    operator delete[](v3);
    *((_QWORD *)this + 2) = 0;
  }
  v4 = (void *)*((_QWORD *)this + 3);
  if ( v4 )
  {
    operator delete[](v4);
    *((_QWORD *)this + 3) = 0;
  }
  if ( *((_QWORD *)this + 1) )
  {
    WdsImgClose();
    *((_QWORD *)this + 1) = 0;
  }
}

```

## disassembly

```asm
0x1800027fc  push    rbx
0x1800027fe  sub     rsp, 20h
0x180002802  mov     rbx, rcx
0x180002805  mov     rcx, [rcx]
0x180002808  test    rcx, rcx
0x18000280b  jz      short loc_18000281D
0x18000280d  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180002814  nop     dword ptr [rax+rax+00h]
0x180002819  and     qword ptr [rbx], 0
0x18000281d  mov     rcx, [rbx+10h]
0x180002821  test    rcx, rcx
0x180002824  jz      short loc_180002837
0x180002826  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18000282d  nop     dword ptr [rax+rax+00h]
0x180002832  and     qword ptr [rbx+10h], 0
0x180002837  mov     rcx, [rbx+18h]
0x18000283b  test    rcx, rcx
0x18000283e  jz      short loc_180002851
0x180002840  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180002847  nop     dword ptr [rax+rax+00h]
0x18000284c  and     qword ptr [rbx+18h], 0
0x180002851  mov     rcx, [rbx+8]
0x180002855  test    rcx, rcx
0x180002858  jz      short loc_18000286B
0x18000285a  call    cs:__imp_WdsImgClose
0x180002861  nop     dword ptr [rax+rax+00h]
0x180002866  and     qword ptr [rbx+8], 0
0x18000286b  add     rsp, 20h
0x18000286f  pop     rbx
0x180002870  retn
```
