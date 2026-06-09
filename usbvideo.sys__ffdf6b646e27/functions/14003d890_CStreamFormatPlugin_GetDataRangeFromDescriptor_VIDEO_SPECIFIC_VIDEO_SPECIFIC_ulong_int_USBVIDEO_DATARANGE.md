# CStreamFormatPlugin::GetDataRangeFromDescriptor(VIDEO_SPECIFIC *,VIDEO_SPECIFIC *,ulong,int,_USBVIDEO_DATARANGE * *)

- ea: `0x14003d890`
- end: `0x14003da66`
- name: `?GetDataRangeFromDescriptor@CStreamFormatPlugin@@UEAAJPEAUVIDEO_SPECIFIC@@0KHPEAPEAU_USBVIDEO_DATARANGE@@@Z`
- size: `470`
- prototype: `__int64 __fastcall(CStreamFormatPlugin *__hidden this, struct VIDEO_SPECIFIC *, struct VIDEO_SPECIFIC *, unsigned int, int, struct _USBVIDEO_DATARANGE **)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x140014050`
- `0x14003d890`
- `0x140040e40`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14003d903`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003d903`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14003d8b1`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14003d8b1`
- `ks!KsAddItemToObjectBag` at `0x14003d8e9`
- `ks!KsAddItemToObjectBag` at `0x14003d8e9`

## pseudocode

```c
__int64 __fastcall CStreamFormatPlugin::GetDataRangeFromDescriptor(
        KSOBJECT_BAG *this,
        struct VIDEO_SPECIFIC *a2,
        struct VIDEO_SPECIFIC *a3,
        __int64 a4,
        int a5,
        struct _USBVIDEO_DATARANGE **a6)
{
  char *PoolWithTag; // rax
  char *v9; // rbx
  NTSTATUS v10; // edi
  __int128 *v11; // rcx
  GUID v12; // xmm0
  __int128 v13; // xmm0

  PoolWithTag = (char *)ExAllocatePoolWithTag((POOL_TYPE)1536, 0x1A0u, 0x56425355u);
  v9 = PoolWithTag;
  if ( !ExPoolZeroingNativelySupported )
  {
    if ( PoolWithTag )
    {
      memset(PoolWithTag, 0, 0x1A0u);
      goto LABEL_4;
    }
    return (unsigned int)-1073741670;
  }
  if ( !PoolWithTag )
    return (unsigned int)-1073741670;
LABEL_4:
  v10 = KsAddItemToObjectBag(this[2], v9, FreeMem);
  if ( v10 >= 0 )
  {
    memset(v9, 0, 0x1A0u);
    v9[76] = *((_BYTE *)a2 + 3);
    if ( (unsigned int)IsEqualGUIDAligned((char *)a2 + 4, &MEDIASUBTYPE_Asf)
      || (unsigned int)IsEqualGUIDAligned(v11, &MEDIASUBTYPE_QTMovie)
      || (unsigned int)IsEqualGUIDAligned(v11, &MEDIASUBTYPE_Avi) )
    {
      v12 = GUID_e436eb83_524f_11ce_9f53_0020af0ba770;
    }
    else
    {
      v12 = GUID_73646976_0000_0010_8000_00aa00389b71;
    }
    *((GUID *)v9 + 7) = v12;
    v13 = *v11;
    *((_DWORD *)v9 + 24) = 320;
    *((GUID *)v9 + 9) = GUID_f72a76a0_eb0a_11d0_ace4_0000c0cc16ba;
    *((_OWORD *)v9 + 8) = v13;
    *((_DWORD *)v9 + 26) = *((_DWORD *)a2 + 5);
    *((_DWORD *)v9 + 25) = 0;
    *(struct tagKS_VIDEOINFOHEADER2 *)(v9 + 304) = FakeVIH2;
    *((GUID *)v9 + 11) = GUID_f72a76a0_eb0a_11d0_ace4_0000c0cc16ba;
    *((_QWORD *)v9 + 35) = FakeVIH2.AvgTimePerFrame;
    *((_DWORD *)v9 + 59) = FakeVIH2.bmiHeader.biWidth;
    *((_DWORD *)v9 + 60) = FakeVIH2.bmiHeader.biHeight;
    *((_DWORD *)v9 + 61) = FakeVIH2.bmiHeader.biWidth;
    *((_DWORD *)v9 + 62) = FakeVIH2.bmiHeader.biHeight;
    *a6 = (struct _USBVIDEO_DATARANGE *)v9;
  }
  else
  {
    ExFreePoolWithTag(v9, 0x56425355u);
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x14003d890  push    rbx
0x14003d892  push    rbp
0x14003d893  push    rsi
0x14003d894  push    rdi
0x14003d895  sub     rsp, 28h
0x14003d899  mov     rsi, rdx
0x14003d89c  mov     rdi, rcx
0x14003d89f  mov     ebp, 1A0h
0x14003d8a4  mov     r8d, 56425355h; Tag
0x14003d8aa  mov     edx, ebp; NumberOfBytes
0x14003d8ac  mov     ecx, 600h; PoolType
0x14003d8b1  call    cs:__imp_ExAllocatePoolWithTag
0x14003d8b8  nop     dword ptr [rax+rax+00h]
0x14003d8bd  cmp     cs:ExPoolZeroingNativelySupported, 0
0x14003d8c4  mov     rbx, rax
0x14003d8c7  jnz     short loc_14003D914
0x14003d8c9  test    rax, rax
0x14003d8cc  jz      short loc_14003D919
0x14003d8ce  mov     r8d, ebp; Size
0x14003d8d1  xor     edx, edx; Val
0x14003d8d3  mov     rcx, rax; void *
0x14003d8d6  call    memset
0x14003d8db  mov     rcx, [rdi+10h]; ObjectBag
0x14003d8df  lea     r8, FreeMem; Free
0x14003d8e6  mov     rdx, rbx; Item
0x14003d8e9  call    cs:__imp_KsAddItemToObjectBag
0x14003d8f0  nop     dword ptr [rax+rax+00h]
0x14003d8f5  mov     edi, eax
0x14003d8f7  mov     rcx, rbx; void *
0x14003d8fa  test    eax, eax
0x14003d8fc  jns     short loc_14003D923
0x14003d8fe  mov     edx, 56425355h; Tag
0x14003d903  call    cs:__imp_ExFreePoolWithTag
0x14003d90a  nop     dword ptr [rax+rax+00h]
0x14003d90f  jmp     loc_14003DA5A
0x14003d914  test    rbx, rbx
0x14003d917  jnz     short loc_14003D8DB
0x14003d919  mov     edi, 0C000009Ah
0x14003d91e  jmp     loc_14003DA5A
0x14003d923  mov     r8, rbp; Size
0x14003d926  xor     edx, edx; Val
0x14003d928  call    memset
0x14003d92d  mov     al, [rsi+3]
0x14003d930  lea     rcx, [rsi+4]
0x14003d934  lea     rdx, MEDIASUBTYPE_Asf
0x14003d93b  mov     [rbx+4Ch], al
0x14003d93e  call    IsEqualGUIDAligned
0x14003d943  test    eax, eax
0x14003d945  jnz     short loc_14003D970
0x14003d947  lea     rdx, MEDIASUBTYPE_QTMovie
0x14003d94e  call    IsEqualGUIDAligned
0x14003d953  test    eax, eax
0x14003d955  jnz     short loc_14003D970
0x14003d957  lea     rdx, MEDIASUBTYPE_Avi
0x14003d95e  call    IsEqualGUIDAligned
0x14003d963  test    eax, eax
0x14003d965  jnz     short loc_14003D970
0x14003d967  movups  xmm0, xmmword ptr cs:_GUID_73646976_0000_0010_8000_00aa00389b71.Data1
0x14003d96e  jmp     short loc_14003D977
0x14003d970  movups  xmm0, xmmword ptr cs:_GUID_e436eb83_524f_11ce_9f53_0020af0ba770.Data1
0x14003d977  movups  xmm2, xmmword ptr cs:_GUID_f72a76a0_eb0a_11d0_ace4_0000c0cc16ba.Data1
0x14003d97e  movdqu  xmmword ptr [rbx+70h], xmm0
0x14003d983  movups  xmm0, xmmword ptr [rcx]
0x14003d986  mov     dword ptr [rbx+60h], 140h
0x14003d98d  movdqu  xmmword ptr [rbx+90h], xmm2
0x14003d995  movdqu  xmmword ptr [rbx+80h], xmm0
0x14003d99d  mov     eax, [rsi+14h]
0x14003d9a0  mov     [rbx+68h], eax
0x14003d9a3  mov     dword ptr [rbx+64h], 0
0x14003d9aa  movaps  xmm0, xmmword ptr cs:?FakeVIH2@@3UtagKS_VIDEOINFOHEADER2@@A; tagKS_VIDEOINFOHEADER2 FakeVIH2
0x14003d9b1  movups  xmmword ptr [rbx+130h], xmm0
0x14003d9b8  movaps  xmm1, xmmword ptr cs:?FakeVIH2@@3UtagKS_VIDEOINFOHEADER2@@A+10h; tagKS_VIDEOINFOHEADER2 FakeVIH2
0x14003d9bf  movups  xmmword ptr [rbx+140h], xmm1
0x14003d9c6  movaps  xmm0, xmmword ptr cs:?FakeVIH2@@3UtagKS_VIDEOINFOHEADER2@@A+20h; tagKS_VIDEOINFOHEADER2 FakeVIH2
0x14003d9cd  movups  xmmword ptr [rbx+150h], xmm0
0x14003d9d4  movaps  xmm1, xmmword ptr cs:?FakeVIH2@@3UtagKS_VIDEOINFOHEADER2@@A+30h; tagKS_VIDEOINFOHEADER2 FakeVIH2
0x14003d9db  movups  xmmword ptr [rbx+160h], xmm1
0x14003d9e2  movaps  xmm0, xmmword ptr cs:?FakeVIH2@@3UtagKS_VIDEOINFOHEADER2@@A+40h; tagKS_VIDEOINFOHEADER2 FakeVIH2
0x14003d9e9  movups  xmmword ptr [rbx+170h], xmm0
0x14003d9f0  movaps  xmm1, xmmword ptr cs:?FakeVIH2@@3UtagKS_VIDEOINFOHEADER2@@A+50h; tagKS_VIDEOINFOHEADER2 FakeVIH2
0x14003d9f7  movups  xmmword ptr [rbx+180h], xmm1
0x14003d9fe  movaps  xmm0, xmmword ptr cs:?FakeVIH2@@3UtagKS_VIDEOINFOHEADER2@@A+60h; tagKS_VIDEOINFOHEADER2 FakeVIH2
0x14003da05  movups  xmmword ptr [rbx+190h], xmm0
0x14003da0c  movdqu  xmmword ptr [rbx+0B0h], xmm2
0x14003da14  mov     rax, qword ptr cs:?FakeVIH2@@3UtagKS_VIDEOINFOHEADER2@@A+28h; tagKS_VIDEOINFOHEADER2 FakeVIH2
0x14003da1b  mov     [rbx+118h], rax
0x14003da22  mov     eax, dword ptr cs:?FakeVIH2@@3UtagKS_VIDEOINFOHEADER2@@A+4Ch; tagKS_VIDEOINFOHEADER2 FakeVIH2
0x14003da28  mov     [rbx+0ECh], eax
0x14003da2e  mov     eax, dword ptr cs:?FakeVIH2@@3UtagKS_VIDEOINFOHEADER2@@A+50h; tagKS_VIDEOINFOHEADER2 FakeVIH2
0x14003da34  mov     [rbx+0F0h], eax
0x14003da3a  mov     eax, dword ptr cs:?FakeVIH2@@3UtagKS_VIDEOINFOHEADER2@@A+4Ch; tagKS_VIDEOINFOHEADER2 FakeVIH2
0x14003da40  mov     [rbx+0F4h], eax
0x14003da46  mov     eax, dword ptr cs:?FakeVIH2@@3UtagKS_VIDEOINFOHEADER2@@A+50h; tagKS_VIDEOINFOHEADER2 FakeVIH2
0x14003da4c  mov     [rbx+0F8h], eax
0x14003da52  mov     rax, [rsp+48h+arg_28]
0x14003da57  mov     [rax], rbx
0x14003da5a  mov     eax, edi
0x14003da5c  add     rsp, 28h
0x14003da60  pop     rdi
0x14003da61  pop     rsi
0x14003da62  pop     rbp
0x14003da63  pop     rbx
0x14003da64  retn
```
