# CMPEG2TSFormatPlugin::GetDataRangeFromDescriptor(VIDEO_SPECIFIC *,VIDEO_SPECIFIC *,ulong,int,_USBVIDEO_DATARANGE * *)

- ea: `0x14003e910`
- end: `0x14003ea8c`
- name: `?GetDataRangeFromDescriptor@CMPEG2TSFormatPlugin@@UEAAJPEAUVIDEO_SPECIFIC@@0KHPEAPEAU_USBVIDEO_DATARANGE@@@Z`
- size: `380`
- prototype: `__int64 __fastcall(CMPEG2TSFormatPlugin *__hidden this, struct VIDEO_SPECIFIC *, struct VIDEO_SPECIFIC *, unsigned int, int, struct _USBVIDEO_DATARANGE **)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x14003e910`
- `0x140040e40`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14003e996`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003e996`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14003e941`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14003e941`
- `ks!KsAddItemToObjectBag` at `0x14003e97c`
- `ks!KsAddItemToObjectBag` at `0x14003e97c`

## pseudocode

```c
__int64 __fastcall CMPEG2TSFormatPlugin::GetDataRangeFromDescriptor(
        KSOBJECT_BAG *this,
        struct VIDEO_SPECIFIC *a2,
        struct VIDEO_SPECIFIC *a3,
        __int64 a4,
        int a5,
        struct _USBVIDEO_DATARANGE **a6)
{
  SIZE_T v8; // rdi
  char *PoolWithTag; // rax
  char *v10; // rbx
  NTSTATUS v11; // ebp
  bool v13; // zf

  v8 = *((_BYTE *)a2 + 4) != 0 ? 176LL : 160LL;
  PoolWithTag = (char *)ExAllocatePoolWithTag((POOL_TYPE)1536, v8, 0x56425355u);
  v10 = PoolWithTag;
  if ( !ExPoolZeroingNativelySupported )
  {
    if ( PoolWithTag )
    {
      memset(PoolWithTag, 0, v8);
      goto LABEL_4;
    }
    return 3221225626LL;
  }
  if ( !PoolWithTag )
    return 3221225626LL;
LABEL_4:
  v11 = KsAddItemToObjectBag(this[2], v10, FreeMem);
  if ( v11 >= 0 )
  {
    memset(v10, 0, v8);
    v10[81] = 0;
    *((_QWORD *)v10 + 5) = 0;
    *((_DWORD *)v10 + 12) = 0;
    v13 = *((_BYTE *)a2 + 4) == 0;
    *((GUID *)v10 + 7) = GUID_e436eb83_524f_11ce_9f53_0020af0ba770;
    if ( v13 )
    {
      *((_DWORD *)v10 + 24) = 64;
      *((_DWORD *)v10 + 26) = 48128;
      *((GUID *)v10 + 9) = GUID_0f6417d6_c318_11d0_a43f_00a0c9223196;
      *((GUID *)v10 + 8) = GUID_e06d8023_db46_11cf_b4d1_00805f6cbbea;
    }
    else
    {
      *((_DWORD *)v10 + 24) = 80;
      *((GUID *)v10 + 9) = GUID_5e3716ca_7217_43bf_b1b9_114cb81f0a30;
      *((GUID *)v10 + 8) = GUID_138aa9a4_1ee2_4c5b_988e_19abfdbc8a11;
      *((_DWORD *)v10 + 26) = *((unsigned __int8 *)a2 + 6) << 8;
      *((_DWORD *)v10 + 40) = *((unsigned __int8 *)a2 + 4);
      *((_DWORD *)v10 + 41) = *((unsigned __int8 *)a2 + 5);
      *((_DWORD *)v10 + 42) = *((unsigned __int8 *)a2 + 6);
    }
    *(_QWORD *)(v10 + 52) = 0;
    *(_QWORD *)(v10 + 60) = 0;
    *(_QWORD *)(v10 + 68) = 0;
    v10[76] = *((_BYTE *)a2 + 3);
    *(_WORD *)(v10 + 77) = 0;
    v10[79] = 0;
    *a6 = (struct _USBVIDEO_DATARANGE *)v10;
    return 0;
  }
  else
  {
    ExFreePoolWithTag(v10, 0x56425355u);
    return (unsigned int)v11;
  }
}

```

## disassembly

```asm
0x14003e910  push    rbx
0x14003e912  push    rbp
0x14003e913  push    rsi
0x14003e914  push    rdi
0x14003e915  push    r14
0x14003e917  sub     rsp, 20h
0x14003e91b  mov     al, [rdx+4]
0x14003e91e  mov     rsi, rdx
0x14003e921  neg     al
0x14003e923  mov     rbp, rcx
0x14003e926  mov     r8d, 56425355h; Tag
0x14003e92c  mov     ecx, 600h; PoolType
0x14003e931  sbb     rdi, rdi
0x14003e934  and     edi, 10h
0x14003e937  add     rdi, 0A0h
0x14003e93e  mov     rdx, rdi; NumberOfBytes
0x14003e941  call    cs:__imp_ExAllocatePoolWithTag
0x14003e948  nop     dword ptr [rax+rax+00h]
0x14003e94d  xor     r14d, r14d
0x14003e950  mov     rbx, rax
0x14003e953  cmp     cs:ExPoolZeroingNativelySupported, r14b
0x14003e95a  jnz     short loc_14003E9A9
0x14003e95c  test    rax, rax
0x14003e95f  jz      short loc_14003E9AE
0x14003e961  mov     r8, rdi; Size
0x14003e964  xor     edx, edx; Val
0x14003e966  mov     rcx, rax; void *
0x14003e969  call    memset
0x14003e96e  mov     rcx, [rbp+10h]; ObjectBag
0x14003e972  lea     r8, FreeMem; Free
0x14003e979  mov     rdx, rbx; Item
0x14003e97c  call    cs:__imp_KsAddItemToObjectBag
0x14003e983  nop     dword ptr [rax+rax+00h]
0x14003e988  mov     ebp, eax
0x14003e98a  mov     rcx, rbx; void *
0x14003e98d  test    eax, eax
0x14003e98f  jns     short loc_14003E9B8
0x14003e991  mov     edx, 56425355h; Tag
0x14003e996  call    cs:__imp_ExFreePoolWithTag
0x14003e99d  nop     dword ptr [rax+rax+00h]
0x14003e9a2  mov     eax, ebp
0x14003e9a4  jmp     loc_14003EA80
0x14003e9a9  test    rbx, rbx
0x14003e9ac  jnz     short loc_14003E96E
0x14003e9ae  mov     eax, 0C000009Ah
0x14003e9b3  jmp     loc_14003EA80
0x14003e9b8  mov     r8, rdi; Size
0x14003e9bb  xor     edx, edx; Val
0x14003e9bd  call    memset
0x14003e9c2  movups  xmm0, xmmword ptr cs:_GUID_e436eb83_524f_11ce_9f53_0020af0ba770.Data1
0x14003e9c9  mov     [rbx+51h], r14b
0x14003e9cd  mov     [rbx+28h], r14
0x14003e9d1  mov     [rbx+30h], r14d
0x14003e9d5  cmp     [rsi+4], r14b
0x14003e9d9  movdqu  xmmword ptr [rbx+70h], xmm0
0x14003e9de  jnz     short loc_14003EA0E
0x14003e9e0  movups  xmm0, xmmword ptr cs:_GUID_0f6417d6_c318_11d0_a43f_00a0c9223196.Data1
0x14003e9e7  mov     dword ptr [rbx+60h], 40h ; '@'
0x14003e9ee  movups  xmm1, xmmword ptr cs:_GUID_e06d8023_db46_11cf_b4d1_00805f6cbbea.Data1
0x14003e9f5  mov     dword ptr [rbx+68h], 0BC00h
0x14003e9fc  movdqu  xmmword ptr [rbx+90h], xmm0
0x14003ea04  movdqu  xmmword ptr [rbx+80h], xmm1
0x14003ea0c  jmp     short loc_14003EA5B
0x14003ea0e  movups  xmm0, xmmword ptr cs:_GUID_5e3716ca_7217_43bf_b1b9_114cb81f0a30.Data1
0x14003ea15  mov     dword ptr [rbx+60h], 50h ; 'P'
0x14003ea1c  movups  xmm1, xmmword ptr cs:_GUID_138aa9a4_1ee2_4c5b_988e_19abfdbc8a11.Data1
0x14003ea23  movdqu  xmmword ptr [rbx+90h], xmm0
0x14003ea2b  movdqu  xmmword ptr [rbx+80h], xmm1
0x14003ea33  movzx   eax, byte ptr [rsi+6]
0x14003ea37  shl     eax, 8
0x14003ea3a  mov     [rbx+68h], eax
0x14003ea3d  movzx   eax, byte ptr [rsi+4]
0x14003ea41  mov     [rbx+0A0h], eax
0x14003ea47  movzx   eax, byte ptr [rsi+5]
0x14003ea4b  mov     [rbx+0A4h], eax
0x14003ea51  movzx   eax, byte ptr [rsi+6]
0x14003ea55  mov     [rbx+0A8h], eax
0x14003ea5b  mov     [rbx+34h], r14
0x14003ea5f  mov     [rbx+3Ch], r14
0x14003ea63  mov     [rbx+44h], r14
0x14003ea67  mov     al, [rsi+3]
0x14003ea6a  mov     [rbx+4Ch], al
0x14003ea6d  mov     rax, [rsp+48h+arg_28]
0x14003ea72  mov     [rbx+4Dh], r14w
0x14003ea77  mov     [rbx+4Fh], r14b
0x14003ea7b  mov     [rax], rbx
0x14003ea7e  xor     eax, eax
0x14003ea80  add     rsp, 20h
0x14003ea84  pop     r14
0x14003ea86  pop     rdi
0x14003ea87  pop     rsi
0x14003ea88  pop     rbp
0x14003ea89  pop     rbx
0x14003ea8a  retn
```
