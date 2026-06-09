# SpMapCallback(_DEVICE_OBJECT *,_LIST_ENTRY *,_LIST_ENTRY *,void *)

- ea: `0x14003be40`
- end: `0x14003c065`
- name: `?SpMapCallback@@YAJPEAU_DEVICE_OBJECT@@PEAU_LIST_ENTRY@@1PEAX@Z`
- size: `549`
- prototype: `__int64 __fastcall(struct _DEVICE_OBJECT *, struct _LIST_ENTRY *, struct _LIST_ENTRY *, void *)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1400268c0`
- `0x14003be40`
- `0x140045ac8`
- `0x140046898`
- `0x140046978`
- `0x1400adc34`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14003c029`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003c03f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003c029`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003c03f`
- `ntoskrnl!IofCompleteRequest` at `0x14003c007`
- `ntoskrnl!IofCompleteRequest` at `0x14003c007`

## pseudocode

```c
__int64 __fastcall SpMapCallback(struct _DEVICE_OBJECT *a1, struct _LIST_ENTRY *a2, struct _LIST_ENTRY *a3, void *a4)
{
  char *DeviceExtension; // r15
  struct _LIST_ENTRY *Flink; // rdx
  struct SDB_RANGES *v7; // rdi
  int v8; // r14d
  _DWORD *v9; // rbp
  int v10; // ebx
  struct _LIST_ENTRY *v11; // rax
  char v12; // cl
  int v13; // eax
  _DWORD *v14; // rax
  __int64 v15; // rdx
  unsigned int v16; // r9d
  struct _LIST_ENTRY *i; // r8
  struct _LIST_ENTRY *v18; // rax
  struct _LIST_ENTRY *Blink; // rcx
  __int64 v20; // rax
  SIO_CACHE *v21; // rcx
  int PendingMapRanges; // eax
  __int64 v23; // rdx
  unsigned int v24; // r12d
  struct _LIST_ENTRY *v25; // rax
  struct _LIST_ENTRY *v26; // rcx
  IRP *p_Blink; // r14
  struct _LIST_ENTRY *v28; // rdx
  __int64 v29; // rax
  int v30; // ecx
  SIO_CACHE *v31; // rcx
  struct SDB_RANGES *v33; // [rsp+60h] [rbp+8h] BYREF

  DeviceExtension = (char *)a1->DeviceExtension;
  Flink = a2->Flink;
  v7 = 0;
  v8 = 0;
  v33 = 0;
  v9 = 0;
  v10 = 0;
  if ( Flink == a2 )
    goto LABEL_14;
  do
  {
    v11 = Flink[1].Flink;
    Flink = Flink->Flink;
    v12 = BYTE1(v11->Flink);
    v13 = v8 + 1;
    if ( v12 == 85 )
      v13 = v8;
    v8 = v13;
  }
  while ( Flink != a2 );
  if ( !v13 )
    goto LABEL_14;
  v14 = SC_ENV::Allocate((unsigned int)(32 * v13) + 40LL, 0x58587053u, 1u, 0);
  v9 = v14;
  if ( !v14 )
  {
    v10 = -1073741670;
    goto LABEL_18;
  }
  v14[1] = v8;
  v16 = 0;
  for ( i = a2->Flink; i != a2; i = i->Flink )
  {
    v18 = i[1].Flink;
    LODWORD(i[-8].Blink) = 0;
    if ( BYTE1(v18->Flink) != 85 )
    {
      Blink = v18[1].Blink;
      v20 = (__int64)Blink + LODWORD(v18->Blink);
      v15 = 32LL * v16++;
      *(_QWORD *)((char *)v9 + v15 + 8) = Blink;
      *(_QWORD *)((char *)v9 + v15 + 16) = v20;
      *(_DWORD *)((char *)v9 + v15 + 32) = 0;
    }
  }
  LOBYTE(v15) = 2;
  v10 = SpMapExtents(DeviceExtension + 8, v15, v9);
  if ( v10 >= 0 )
  {
LABEL_14:
    v21 = (SIO_CACHE *)*((_QWORD *)DeviceExtension + 18);
    if ( v21 )
    {
      PendingMapRanges = SIO_CACHE::GetPendingMapRanges(v21, &v33);
      v7 = v33;
      v10 = PendingMapRanges;
      if ( PendingMapRanges >= 0 )
      {
        if ( v33 )
        {
          LOBYTE(v23) = 11;
          v10 = SpMapExtents(DeviceExtension + 8, v23, v33);
        }
      }
    }
  }
LABEL_18:
  v24 = 0;
  while ( 1 )
  {
    v25 = a2->Flink;
    if ( a2->Flink == a2 )
      break;
    if ( v25->Blink != a2 || (v26 = v25->Flink, v25->Flink->Blink != v25) )
      __fastfail(3u);
    a2->Flink = v26;
    p_Blink = (IRP *)&v25[-11].Blink;
    v26->Blink = a2;
    v28 = v25[1].Flink;
    LODWORD(v25[-8].Blink) = v10;
    if ( BYTE1(v28->Flink) == 85 || v10 < 0 )
    {
      v30 = v10;
    }
    else
    {
      v29 = ++v24;
      v30 = v9[8 * v29];
      p_Blink->IoStatus.Status = v30;
    }
    if ( *((_QWORD *)DeviceExtension + 18) && v7 && v30 >= 0 )
      p_Blink->IoStatus.Status = SIO_CACHE::GetPendingMapStatus(
                                   *((SIO_CACHE **)DeviceExtension + 18),
                                   (unsigned __int64)v28[1].Blink,
                                   LODWORD(v28->Blink),
                                   v7,
                                   v10);
    v31 = (SIO_CACHE *)*((_QWORD *)DeviceExtension + 18);
    if ( v31 )
    {
      if ( v7 )
        SIO_CACHE::CompleteMap(v31, v7, v10);
    }
    IofCompleteRequest(p_Blink, 0);
  }
  if ( v7 )
    ExFreePoolWithTag(v7, 0);
  if ( v9 )
    ExFreePoolWithTag(v9, 0);
  return 0;
}

```

## disassembly

```asm
0x14003be40  mov     [rsp+arg_8], rbx
0x14003be45  mov     [rsp+arg_10], rbp
0x14003be4a  push    rsi
0x14003be4b  push    rdi
0x14003be4c  push    r12
0x14003be4e  push    r14
0x14003be50  push    r15
0x14003be52  sub     rsp, 30h
0x14003be56  mov     r15, [rcx+40h]
0x14003be5a  mov     rsi, rdx
0x14003be5d  mov     rdx, [rdx]
0x14003be60  xor     edi, edi
0x14003be62  xor     r14d, r14d
0x14003be65  mov     [rsp+58h+arg_0], rdi
0x14003be6a  xor     ebp, ebp
0x14003be6c  xor     ebx, ebx
0x14003be6e  cmp     rdx, rsi
0x14003be71  jz      loc_14003BF1F
0x14003be77  mov     rax, [rdx+10h]
0x14003be7b  mov     rdx, [rdx]
0x14003be7e  mov     cl, [rax+1]
0x14003be81  lea     eax, [r14+1]
0x14003be85  cmp     cl, 55h ; 'U'
0x14003be88  cmovz   eax, r14d
0x14003be8c  mov     r14d, eax
0x14003be8f  cmp     rdx, rsi
0x14003be92  jnz     short loc_14003BE77
0x14003be94  test    eax, eax
0x14003be96  jz      loc_14003BF1F
0x14003be9c  mov     ecx, eax
0x14003be9e  xor     r9d, r9d; unsigned int
0x14003bea1  shl     ecx, 5
0x14003bea4  mov     r8b, 1; unsigned __int8
0x14003bea7  add     rcx, 28h ; '('; unsigned __int64
0x14003beab  mov     edx, 58587053h; unsigned int
0x14003beb0  call    ?Allocate@SC_ENV@@SAPEAX_KKEK@Z; SC_ENV::Allocate(unsigned __int64,ulong,uchar,ulong)
0x14003beb5  mov     rbp, rax
0x14003beb8  test    rax, rax
0x14003bebb  jnz     short loc_14003BEC7
0x14003bebd  mov     ebx, 0C000009Ah
0x14003bec2  jmp     loc_14003BF55
0x14003bec7  mov     [rax+4], r14d
0x14003becb  xor     r9d, r9d
0x14003bece  mov     r8, [rsi]
0x14003bed1  jmp     short loc_14003BF06
0x14003bed3  mov     rax, [r8+10h]
0x14003bed7  mov     [r8-78h], ebx
0x14003bedb  cmp     byte ptr [rax+1], 55h ; 'U'
0x14003bedf  jz      short loc_14003BF03
0x14003bee1  mov     rcx, [rax+18h]
0x14003bee5  mov     eax, [rax+8]
0x14003bee8  mov     edx, r9d
0x14003beeb  add     rax, rcx
0x14003beee  shl     rdx, 5
0x14003bef2  inc     r9d
0x14003bef5  mov     [rdx+rbp+8], rcx
0x14003befa  mov     [rdx+rbp+10h], rax
0x14003beff  mov     [rdx+rbp+20h], ebx
0x14003bf03  mov     r8, [r8]
0x14003bf06  cmp     r8, rsi
0x14003bf09  jnz     short loc_14003BED3
0x14003bf0b  mov     r8, rbp
0x14003bf0e  lea     rcx, [r15+8]
0x14003bf12  mov     dl, 2
0x14003bf14  call    ?SpMapExtents@@YAJPEAVSP_DEVICE@@W4_SC_SPACE_USAGE@@PEAVSDB_RANGES@@@Z; SpMapExtents(SP_DEVICE *,_SC_SPACE_USAGE,SDB_RANGES *)
0x14003bf19  mov     ebx, eax
0x14003bf1b  test    eax, eax
0x14003bf1d  js      short loc_14003BF55
0x14003bf1f  mov     rcx, [r15+90h]; this
0x14003bf26  test    rcx, rcx
0x14003bf29  jz      short loc_14003BF55
0x14003bf2b  lea     rdx, [rsp+58h+arg_0]; struct SDB_RANGES **
0x14003bf30  call    ?GetPendingMapRanges@SIO_CACHE@@QEAAJPEAPEAVSDB_RANGES@@@Z; SIO_CACHE::GetPendingMapRanges(SDB_RANGES * *)
0x14003bf35  mov     rdi, [rsp+58h+arg_0]
0x14003bf3a  mov     ebx, eax
0x14003bf3c  test    eax, eax
0x14003bf3e  js      short loc_14003BF55
0x14003bf40  test    rdi, rdi
0x14003bf43  jz      short loc_14003BF55
0x14003bf45  mov     r8, rdi
0x14003bf48  lea     rcx, [r15+8]
0x14003bf4c  mov     dl, 0Bh
0x14003bf4e  call    ?SpMapExtents@@YAJPEAVSP_DEVICE@@W4_SC_SPACE_USAGE@@PEAVSDB_RANGES@@@Z; SpMapExtents(SP_DEVICE *,_SC_SPACE_USAGE,SDB_RANGES *)
0x14003bf53  mov     ebx, eax
0x14003bf55  xor     r12d, r12d
0x14003bf58  mov     rax, [rsi]
0x14003bf5b  cmp     rax, rsi
0x14003bf5e  jz      loc_14003C01F
0x14003bf64  cmp     [rax+8], rsi
0x14003bf68  jnz     loc_14003C018
0x14003bf6e  mov     rcx, [rax]
0x14003bf71  cmp     [rcx+8], rax
0x14003bf75  jnz     loc_14003C018
0x14003bf7b  mov     [rsi], rcx
0x14003bf7e  lea     r14, [rax-0A8h]
0x14003bf85  mov     [rcx+8], rsi
0x14003bf89  mov     rdx, [r14+0B8h]
0x14003bf90  mov     [r14+30h], ebx
0x14003bf94  cmp     byte ptr [rdx+1], 55h ; 'U'
0x14003bf98  jz      short loc_14003BFB4
0x14003bf9a  test    ebx, ebx
0x14003bf9c  js      short loc_14003BFB4
0x14003bf9e  mov     eax, r12d
0x14003bfa1  inc     rax
0x14003bfa4  shl     rax, 5
0x14003bfa8  inc     r12d
0x14003bfab  mov     ecx, [rax+rbp]
0x14003bfae  mov     [r14+30h], ecx
0x14003bfb2  jmp     short loc_14003BFB6
0x14003bfb4  mov     ecx, ebx
0x14003bfb6  mov     rax, [r15+90h]
0x14003bfbd  test    rax, rax
0x14003bfc0  jz      short loc_14003BFE6
0x14003bfc2  test    rdi, rdi
0x14003bfc5  jz      short loc_14003BFE6
0x14003bfc7  test    ecx, ecx
0x14003bfc9  js      short loc_14003BFE6
0x14003bfcb  mov     r8d, [rdx+8]; unsigned __int64
0x14003bfcf  mov     r9, rdi; struct SDB_RANGES *
0x14003bfd2  mov     rdx, [rdx+18h]; unsigned __int64
0x14003bfd6  mov     rcx, rax; this
0x14003bfd9  mov     [rsp+58h+var_38], ebx; int
0x14003bfdd  call    ?GetPendingMapStatus@SIO_CACHE@@QEAAJ_K0PEAVSDB_RANGES@@J@Z; SIO_CACHE::GetPendingMapStatus(unsigned __int64,unsigned __int64,SDB_RANGES *,long)
0x14003bfe2  mov     [r14+30h], eax
0x14003bfe6  mov     rcx, [r15+90h]; this
0x14003bfed  test    rcx, rcx
0x14003bff0  jz      short loc_14003C002
0x14003bff2  test    rdi, rdi
0x14003bff5  jz      short loc_14003C002
0x14003bff7  mov     r8d, ebx; int
0x14003bffa  mov     rdx, rdi; struct SDB_RANGES *
0x14003bffd  call    ?CompleteMap@SIO_CACHE@@QEAAXPEAVSDB_RANGES@@J@Z; SIO_CACHE::CompleteMap(SDB_RANGES *,long)
0x14003c002  xor     edx, edx; PriorityBoost
0x14003c004  mov     rcx, r14; Irp
0x14003c007  call    cs:__imp_IofCompleteRequest
0x14003c00e  nop     dword ptr [rax+rax+00h]
0x14003c013  jmp     loc_14003BF58
0x14003c018  mov     ecx, 3
0x14003c01d  int     29h; Win8: RtlFailFast(ecx)
0x14003c01f  test    rdi, rdi
0x14003c022  jz      short loc_14003C035
0x14003c024  xor     edx, edx; Tag
0x14003c026  mov     rcx, rdi; P
0x14003c029  call    cs:__imp_ExFreePoolWithTag
0x14003c030  nop     dword ptr [rax+rax+00h]
0x14003c035  test    rbp, rbp
0x14003c038  jz      short loc_14003C04B
0x14003c03a  xor     edx, edx; Tag
0x14003c03c  mov     rcx, rbp; P
0x14003c03f  call    cs:__imp_ExFreePoolWithTag
0x14003c046  nop     dword ptr [rax+rax+00h]
0x14003c04b  mov     rbx, [rsp+58h+arg_8]
0x14003c050  xor     eax, eax
0x14003c052  mov     rbp, [rsp+58h+arg_10]
0x14003c057  add     rsp, 30h
0x14003c05b  pop     r15
0x14003c05d  pop     r14
0x14003c05f  pop     r12
0x14003c061  pop     rdi
0x14003c062  pop     rsi
0x14003c063  retn
```
