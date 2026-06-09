# CImageCache::InsertImageByPriorityOrder(CImageCache::Image *)

- ea: `0x1800092ec`
- end: `0x18000942a`
- name: `?InsertImageByPriorityOrder@CImageCache@@AEAAKPEAUImage@1@@Z`
- size: `318`
- prototype: `unsigned int __fastcall(CImageCache *__hidden this, struct Image *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180008494`

## callees

- `0x1800029e8`
- `0x1800080d0`
- `0x180008150`
- `0x180008c70`
- `0x1800092ec`
- `0x18000aeac`

## import_xrefs

- `WdsCommonLib!?ReaderRelease@CMRSWLock@@QEAAXXZ` at `0x180009402`
- `WdsCommonLib!?ReaderRelease@CMRSWLock@@QEAAXXZ` at `0x180009402`

## string_xrefs

- `0x180009345`: `base\eco\wds\wdssrv\wdsimgsrv\src\imagecache.cpp`
- `0x1800093c2`: `base\eco\wds\wdssrv\wdsimgsrv\src\imagecache.cpp`
- `0x1800093e0`: `base\eco\wds\wdssrv\wdsimgsrv\src\imagecache.cpp`

## pseudocode

```c
__int64 __fastcall CImageCache::InsertImageByPriorityOrder(CImageCache *this, struct Image *a2, int a3)
{
  unsigned int v5; // r15d
  __int64 *v6; // rbx
  __int64 i; // rsi
  char *v8; // rcx
  __int64 Item; // rdi
  __int64 v10; // rdx
  __int64 v11; // rdx
  __int64 v12; // r9
  __int64 v13; // r10
  __int64 v14; // rdx
  CMRSWLock *v16; // [rsp+20h] [rbp-28h] BYREF
  int v17; // [rsp+28h] [rbp-20h]
  __int64 v18; // [rsp+50h] [rbp+8h] BYREF

  v18 = 0;
  CAutoReaderLock::CAutoReaderLock((CAutoReaderLock *)&v16, this, a3);
  v5 = *((_DWORD *)a2 + 16);
  v6 = (__int64 *)((char *)this + 128);
  for ( i = 0; ; i = (unsigned int)(i + 1) )
  {
    v8 = (char *)this + 128;
    if ( (unsigned int)i >= *((_DWORD *)this + 35) )
    {
      LODWORD(Item) = CDynArray<CImageCache::Image *,CDeallocatePointer>::AddItem(v8, a2);
      ElValidateWin32_0((unsigned int)Item, v14, "base\\eco\\wds\\wdssrv\\wdsimgsrv\\src\\imagecache.cpp", 1044);
      goto LABEL_15;
    }
    Item = (unsigned int)CDynArray<CWdsMetadataEntry *,CDeallocatePointer>::GetItem(v8, (unsigned int)i, &v18);
    if ( (unsigned int)ElValidateWin32_0(Item, v10, "base\\eco\\wds\\wdssrv\\wdsimgsrv\\src\\imagecache.cpp", 1020) )
      goto LABEL_15;
    if ( *(_DWORD *)(v18 + 64) > v5 )
      break;
  }
  if ( (unsigned int)i <= *((_DWORD *)this + 35) )
  {
    LODWORD(Item) = CDynArray<CImageCache::Image *,CDeallocatePointer>::Grow((char *)this + 128);
    if ( !(_DWORD)Item )
    {
      v12 = *((unsigned int *)this + 35);
      if ( (unsigned int)v12 > (unsigned int)i )
      {
        v13 = 8 * v12;
        do
        {
          v11 = *v6;
          v12 = (unsigned int)(v12 - 1);
          *(_QWORD *)(v13 + *v6) = *(_QWORD *)(*v6 + 8 * v12);
          v13 -= 8;
        }
        while ( (unsigned int)v12 > (unsigned int)i );
      }
      *(_QWORD *)(*v6 + 8 * i) = a2;
      ++*((_DWORD *)this + 35);
    }
  }
  else
  {
    LODWORD(Item) = 1413;
  }
  ElValidateWin32_0((unsigned int)Item, v11, "base\\eco\\wds\\wdssrv\\wdsimgsrv\\src\\imagecache.cpp", 1032);
LABEL_15:
  if ( v17 == 1 )
    CMRSWLock::ReaderRelease(v16);
  return (unsigned int)Item;
}

```

## disassembly

```asm
0x1800092ec  mov     rax, rsp
0x1800092ef  mov     [rax+10h], rbx
0x1800092f3  mov     [rax+18h], rbp
0x1800092f7  mov     [rax+20h], rsi
0x1800092fb  push    rdi
0x1800092fc  push    r14
0x1800092fe  push    r15
0x180009300  sub     rsp, 30h
0x180009304  and     qword ptr [rax+8], 0
0x180009309  mov     r14, rdx
0x18000930c  mov     rdx, rcx; struct CMRSWLock *
0x18000930f  mov     rbp, rcx
0x180009312  lea     rcx, [rax-28h]; this
0x180009316  call    ??0CAutoReaderLock@@QEAA@PEAVCMRSWLock@@H@Z; CAutoReaderLock::CAutoReaderLock(CMRSWLock *,int)
0x18000931b  mov     r15d, [r14+40h]
0x18000931f  lea     rbx, [rbp+80h]
0x180009326  xor     esi, esi
0x180009328  mov     rcx, rbx
0x18000932b  cmp     esi, [rbp+8Ch]
0x180009331  jnb     loc_1800093D2
0x180009337  lea     r8, [rsp+48h+arg_0]
0x18000933c  mov     edx, esi
0x18000933e  call    ?GetItem@?$CDynArray@PEAVCWdsMetadataEntry@@VCDeallocatePointer@@@@QEAAKKAEAPEAVCWdsMetadataEntry@@@Z; CDynArray<CWdsMetadataEntry *,CDeallocatePointer>::GetItem(ulong,CWdsMetadataEntry * &)
0x180009343  mov     ecx, eax
0x180009345  lea     r8, aBaseEcoWdsWdss_0; "base\\eco\\wds\\wdssrv\\wdsimgsrv\\src"...
0x18000934c  mov     r9d, 3FCh
0x180009352  mov     edi, eax
0x180009354  call    ElValidateWin32_0
0x180009359  test    eax, eax
0x18000935b  jnz     loc_1800093F0
0x180009361  mov     rax, [rsp+48h+arg_0]
0x180009366  cmp     [rax+40h], r15d
0x18000936a  ja      short loc_180009370
0x18000936c  inc     esi
0x18000936e  jmp     short loc_180009328
0x180009370  cmp     esi, [rbx+0Ch]
0x180009373  jbe     short loc_18000937C
0x180009375  mov     edi, 585h
0x18000937a  jmp     short loc_1800093BC
0x18000937c  mov     rcx, rbx
0x18000937f  call    ?Grow@?$CDynArray@PEAUImage@CImageCache@@VCDeallocatePointer@@@@AEAAKXZ; CDynArray<CImageCache::Image *,CDeallocatePointer>::Grow(void)
0x180009384  mov     edi, eax
0x180009386  test    eax, eax
0x180009388  jnz     short loc_1800093BC
0x18000938a  mov     r9d, [rbx+0Ch]
0x18000938e  cmp     r9d, esi
0x180009391  jbe     short loc_1800093B2
0x180009393  lea     r10, ds:0[r9*8]
0x18000939b  mov     rdx, [rbx]
0x18000939e  dec     r9d
0x1800093a1  mov     rcx, [rdx+r9*8]
0x1800093a5  mov     [r10+rdx], rcx
0x1800093a9  lea     r10, [r10-8]
0x1800093ad  cmp     r9d, esi
0x1800093b0  ja      short loc_18000939B
0x1800093b2  mov     rax, [rbx]
0x1800093b5  mov     [rax+rsi*8], r14
0x1800093b9  inc     dword ptr [rbx+0Ch]
0x1800093bc  mov     r9d, 408h
0x1800093c2  lea     r8, aBaseEcoWdsWdss_0; "base\\eco\\wds\\wdssrv\\wdsimgsrv\\src"...
0x1800093c9  mov     ecx, edi
0x1800093cb  call    ElValidateWin32_0
0x1800093d0  jmp     short loc_1800093F0
0x1800093d2  mov     rdx, r14
0x1800093d5  call    ?AddItem@?$CDynArray@PEAUImage@CImageCache@@VCDeallocatePointer@@@@QEAAKPEAUImage@CImageCache@@@Z; CDynArray<CImageCache::Image *,CDeallocatePointer>::AddItem(CImageCache::Image *)
0x1800093da  mov     r9d, 414h
0x1800093e0  lea     r8, aBaseEcoWdsWdss_0; "base\\eco\\wds\\wdssrv\\wdsimgsrv\\src"...
0x1800093e7  mov     ecx, eax
0x1800093e9  mov     edi, eax
0x1800093eb  call    ElValidateWin32_0
0x1800093f0  mov     eax, [rsp+48h+var_20]
0x1800093f4  test    eax, eax
0x1800093f6  jz      short loc_18000940E
0x1800093f8  cmp     eax, 1
0x1800093fb  jnz     short loc_18000940E
0x1800093fd  mov     rcx, [rsp+48h+var_28]
0x180009402  call    cs:__imp_?ReaderRelease@CMRSWLock@@QEAAXXZ; CMRSWLock::ReaderRelease(void)
0x180009409  nop     dword ptr [rax+rax+00h]
0x18000940e  mov     rbx, [rsp+48h+arg_8]
0x180009413  mov     eax, edi
0x180009415  mov     rbp, [rsp+48h+arg_10]
0x18000941a  mov     rsi, [rsp+48h+arg_18]
0x18000941f  add     rsp, 30h
0x180009423  pop     r15
0x180009425  pop     r14
0x180009427  pop     rdi
0x180009428  retn
```
