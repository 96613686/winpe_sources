# WanpNdisOpenAdapter

- ea: `0x140002350`
- end: `0x14000243c`
- name: `WanpNdisOpenAdapter`
- size: `236`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140002e60`

## callees

- `0x140002350`
- `0x140019970`

## import_xrefs

- `NDIS!NdisOpenAdapterEx` at `0x140002414`
- `NDIS!NdisOpenAdapterEx` at `0x140002414`

## pseudocode

```c
NDIS_STATUS __fastcall WanpNdisOpenAdapter(__int64 a1, void *a2, char a3)
{
  int *v4; // rax
  unsigned int v5; // ebx
  PVOID *v6; // rdx
  UINT v7; // ecx
  char *v8; // rax
  int *v9; // rax
  UINT v10; // ecx
  NDIS_HANDLE v11; // rcx
  NDIS_STATUS result; // eax
  struct _NDIS_OPEN_PARAMETERS v13; // [rsp+30h] [rbp-48h] BYREF

  *(_QWORD *)&v13.Header.Type = 3670407;
  *(&v13.MediumArraySize + 1) = 0;
  *(&v13.FrameTypeArraySize + 1) = 0;
  v13.AdapterName = *(PNDIS_STRING *)(a1 + 16);
  v4 = &dword_1400091C4;
  v5 = 212578788;
  if ( !a3 )
    v4 = &dword_140009414;
  v6 = (PVOID *)&qword_1400099E8;
  v7 = dword_1400091C0;
  if ( !a3 )
    v7 = dword_140009410;
  v13.MediumArray = (PNDIS_MEDIUM)v4;
  v8 = byte_140009A28;
  v13.MediumArraySize = v7;
  if ( !a3 )
    v8 = byte_140009B48;
  v13.SelectedMediumIndex = (PUINT)v8;
  v9 = &dword_1400091D4;
  if ( !a3 )
    v9 = &dword_140009424;
  v10 = dword_1400091D0;
  if ( !a3 )
    v10 = dword_140009420;
  v13.FrameTypeArray = (PNET_FRAME_TYPE)v9;
  if ( !a3 )
    v5 = 212578790;
  v13.FrameTypeArraySize = v10;
  v11 = (NDIS_HANDLE)qword_140009160;
  if ( !a3 )
  {
    v11 = NdisProtocolHandle;
    v6 = &NdisBindingHandle;
  }
  result = NdisOpenAdapterEx(v11, (NDIS_HANDLE)v5, &v13, a2, v6);
  if ( result != 259 )
  {
    WanNdisOpenAdapterComplete(v5, result);
    return 259;
  }
  return result;
}

```

## disassembly

```asm
0x140002350  mov     r11, rsp
0x140002353  push    rbx
0x140002354  sub     rsp, 70h
0x140002358  xor     eax, eax
0x14000235a  mov     qword ptr [r11-48h], 380187h
0x140002362  mov     [rsp+78h+var_2C], eax
0x140002366  test    r8b, r8b
0x140002369  mov     [rsp+78h+var_14], eax
0x14000236d  lea     r8, [r11-48h]; OpenParameters
0x140002371  mov     rax, [rcx+10h]
0x140002375  mov     r9, rdx; BindContext
0x140002378  mov     [r11-40h], rax
0x14000237c  lea     rcx, dword_140009414
0x140002383  lea     rax, dword_1400091C4
0x14000238a  mov     ebx, 0CABB1E4h
0x14000238f  cmovz   rax, rcx
0x140002393  lea     rdx, qword_1400099E8
0x14000239a  mov     ecx, cs:dword_1400091C0
0x1400023a0  cmovz   ecx, cs:dword_140009410
0x1400023a7  mov     [r11-38h], rax
0x1400023ab  lea     rax, byte_140009A28
0x1400023b2  mov     [rsp+78h+var_30], ecx
0x1400023b6  lea     rcx, byte_140009B48
0x1400023bd  cmovz   rax, rcx
0x1400023c1  lea     rcx, dword_140009424
0x1400023c8  mov     [r11-28h], rax
0x1400023cc  lea     rax, dword_1400091D4
0x1400023d3  cmovz   rax, rcx
0x1400023d7  mov     ecx, cs:dword_1400091D0
0x1400023dd  cmovz   ecx, cs:dword_140009420
0x1400023e4  mov     [r11-20h], rax
0x1400023e8  mov     eax, 0CABB1E6h
0x1400023ed  cmovz   ebx, eax
0x1400023f0  mov     [rsp+78h+var_18], ecx
0x1400023f4  mov     rcx, cs:qword_140009160
0x1400023fb  lea     rax, NdisBindingHandle
0x140002402  cmovz   rcx, cs:NdisProtocolHandle; NdisProtocolHandle
0x14000240a  cmovz   rdx, rax
0x14000240e  mov     [r11-58h], rdx
0x140002412  mov     edx, ebx; ProtocolBindingContext
0x140002414  call    cs:__imp_NdisOpenAdapterEx
0x14000241b  nop     dword ptr [rax+rax+00h]
0x140002420  cmp     eax, 103h
0x140002425  jz      short loc_140002435
0x140002427  mov     edx, eax
0x140002429  mov     ecx, ebx
0x14000242b  call    WanNdisOpenAdapterComplete
0x140002430  mov     eax, 103h
0x140002435  add     rsp, 70h
0x140002439  pop     rbx
0x14000243a  retn
```
