# WDSParseImageInformation

- ea: `0x1800037c0`
- end: `0x180003873`
- name: `WDSParseImageInformation`
- size: `179`
- prototype: `__int64 __fastcall(unsigned __int8 *, unsigned __int64, _DWORD *)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config`

## callees

- `0x18000284c`
- `0x180003208`
- `0x1800037c0`
- `0x18000fee5`
- `0x180011010`

## import_xrefs

- `ImageLib!DepImgOpenImageInfoFromXML` at `0x180003800`
- `ImageLib!DepImgOpenImageInfoFromXML` at `0x180003800`

## pseudocode

```c
__int64 __fastcall WDSParseImageInformation(unsigned __int8 *a1, unsigned __int64 a2, _DWORD *a3)
{
  __int64 v6; // rbx
  __int64 v7; // rdx
  __int64 v8; // r8
  __int64 v9; // rdx
  __int64 v10; // r8
  char *v11; // rcx
  struct IDepImageInfo *v13; // [rsp+40h] [rbp+18h] BYREF

  v13 = 0;
  memset_0(a3, 0, 0xD8u);
  a3[36] = -1;
  v6 = (unsigned int)DepImgOpenImageInfoFromXML(a1, a2, &v13);
  if ( (int)ElValidateHr(v6, v7, v8, 861) >= 0 )
  {
    v6 = (unsigned int)WDSGetImageInformationFromImageInfo(v13, (struct _WDS_IMAGE_INFO *)a3);
    ElValidateHr(v6, v9, v10, 864);
  }
  if ( v13 )
  {
    v11 = (char *)v13 + *(int *)(*((_QWORD *)v13 + 1) + 4LL) + 8;
    (*(void (__fastcall **)(char *))(*(_QWORD *)v11 + 16LL))(v11);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800037c0  mov     [rsp+arg_0], rbx
0x1800037c5  mov     [rsp+arg_8], rsi
0x1800037ca  push    rdi
0x1800037cb  sub     rsp, 20h
0x1800037cf  and     [rsp+28h+arg_10], 0
0x1800037d5  mov     rsi, r8
0x1800037d8  mov     rbx, rdx
0x1800037db  mov     rdi, rcx
0x1800037de  mov     rcx, rsi; void *
0x1800037e1  xor     edx, edx; Val
0x1800037e3  mov     r8d, 0D8h; Size
0x1800037e9  call    memset_0
0x1800037ee  or      dword ptr [rsi+90h], 0FFFFFFFFh
0x1800037f5  lea     r8, [rsp+28h+arg_10]
0x1800037fa  mov     rdx, rbx
0x1800037fd  mov     rcx, rdi
0x180003800  call    cs:__imp_?DepImgOpenImageInfoFromXML@@YAJPEAE_KPEAPEAVIDepImageInfo@@@Z; DepImgOpenImageInfoFromXML(uchar *,unsigned __int64,IDepImageInfo * *)
0x180003807  nop     dword ptr [rax+rax+00h]
0x18000380c  mov     ecx, eax
0x18000380e  mov     r9d, 35Dh
0x180003814  mov     ebx, eax
0x180003816  call    ElValidateHr
0x18000381b  test    eax, eax
0x18000381d  js      short loc_18000383B
0x18000381f  mov     rcx, [rsp+28h+arg_10]; struct IDepImageInfo *
0x180003824  mov     rdx, rsi; struct _WDS_IMAGE_INFO *
0x180003827  call    ?WDSGetImageInformationFromImageInfo@@YAJPEAVIDepImageInfo@@PEAU_WDS_IMAGE_INFO@@@Z; WDSGetImageInformationFromImageInfo(IDepImageInfo *,_WDS_IMAGE_INFO *)
0x18000382c  mov     r9d, 360h
0x180003832  mov     ecx, eax
0x180003834  mov     ebx, eax
0x180003836  call    ElValidateHr
0x18000383b  mov     rdx, [rsp+28h+arg_10]
0x180003840  test    rdx, rdx
0x180003843  jz      short loc_180003860
0x180003845  mov     rax, [rdx+8]
0x180003849  add     rdx, 8
0x18000384d  movsxd  rcx, dword ptr [rax+4]
0x180003851  add     rcx, rdx
0x180003854  mov     rax, [rcx]
0x180003857  mov     rax, [rax+10h]
0x18000385b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003860  mov     rsi, [rsp+28h+arg_8]
0x180003865  mov     eax, ebx
0x180003867  mov     rbx, [rsp+28h+arg_0]
0x18000386c  add     rsp, 20h
0x180003870  pop     rdi
0x180003871  retn
```
