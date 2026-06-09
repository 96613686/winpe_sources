# TdhpGetPropertyOffsetAndSize(ulong,ushort,_GUID *,_EVENT_DESCRIPTOR const *,uchar *,ulong,ulong,_PROPERTY_DATA_DESCRIPTOR *,ulong *,ulong *)

- ea: `0x1800270cc`
- end: `0x180027379`
- name: `?TdhpGetPropertyOffsetAndSize@@YAKKGPEAU_GUID@@PEBU_EVENT_DESCRIPTOR@@PEAEKKPEAU_PROPERTY_DATA_DESCRIPTOR@@PEAK4@Z`
- size: `685`
- prototype: `unsigned int __usercall@<eax>(unsigned int@<ecx>, unsigned __int16@<dx>, struct _GUID *@<r8>, const struct _EVENT_DESCRIPTOR *@<r9>, unsigned __int8 *, unsigned int, unsigned int, struct _PROPERTY_DATA_DESCRIPTOR *, unsigned int *, unsigned int *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180024150`

## callees

- `0x180001084`
- `0x1800022f0`
- `0x180004fb0`
- `0x1800064d0`
- `0x1800076e0`
- `0x180018c00`
- `0x180021490`
- `0x1800270cc`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180027337`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180027337`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180027329`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180027329`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18002716c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18002716c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18002730b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18002730b`

## pseudocode

```c
// Hidden C++ exception states: #wind=1 #try_helpers=1
__int64 __fastcall TdhpGetPropertyOffsetAndSize(
        unsigned int a1,
        __int16 a2,
        struct _GUID *a3,
        const struct _EVENT_DESCRIPTOR *a4,
        unsigned __int8 *a5,
        unsigned int a6,
        unsigned int a7,
        struct _PROPERTY_DATA_DESCRIPTOR *a8,
        unsigned int *a9,
        unsigned int *a10)
{
  RTL_SRWLOCK *v14; // rax
  RTL_SRWLOCK *v15; // rsi
  unsigned int *TraceEventInfoFromMofInfo; // rax
  unsigned int *v18; // r14
  unsigned int v19; // ebx
  unsigned __int64 v20; // rbx
  __int64 v21; // r15
  unsigned __int64 v22; // rcx
  __int64 v23; // rax
  size_t v24; // rbx
  unsigned int MatchedProperty; // eax
  HANDLE ProcessHeap; // rax
  unsigned int v27; // [rsp+80h] [rbp-78h] BYREF
  unsigned int v28; // [rsp+84h] [rbp-74h] BYREF
  __int64 v29[3]; // [rsp+88h] [rbp-70h] BYREF
  __int128 v30; // [rsp+A0h] [rbp-58h] BYREF
  __int64 v31; // [rsp+B0h] [rbp-48h]

  v29[0] = 0;
  v30 = 0;
  v31 = 0;
  v28 = 0;
  v27 = 0;
  if ( !a5 || !a6 )
    return 13;
  v14 = (RTL_SRWLOCK *)TdhpCacheLockEntry(0, (__int64)a3);
  v15 = v14;
  v29[1] = (__int64)v14;
  if ( !v14 )
  {
    if ( (_QWORD)v30 )
      std::_Deallocate<16>(v30, (v31 - v30) & 0xFFFFFFFFFFFFFFFCuLL);
    return 8;
  }
  AcquireSRWLockShared(v14);
  TraceEventInfoFromMofInfo = (unsigned int *)TdhpGetTraceEventInfoFromMofInfo(
                                                a1,
                                                a2,
                                                (__int64)v15,
                                                a3,
                                                (__int64)a4,
                                                0,
                                                0,
                                                v29);
  v18 = TraceEventInfoFromMofInfo;
  v29[2] = (__int64)TraceEventInfoFromMofInfo;
  if ( TraceEventInfoFromMofInfo )
  {
    v20 = TraceEventInfoFromMofInfo[25];
    v21 = *((_QWORD *)&v30 + 1);
    v22 = (__int64)(*((_QWORD *)&v30 + 1) - v30) >> 2;
    if ( v20 >= v22 )
    {
      if ( v20 <= v22 )
        goto LABEL_16;
      if ( v20 > (v31 - (__int64)v30) >> 2 )
      {
        std::vector<unsigned long>::_Resize_reallocate<std::_Value_init_tag>(&v30, v20);
        goto LABEL_16;
      }
      v24 = 4 * (v20 - v22);
      memset_0(*((void **)&v30 + 1), 0, v24);
      v23 = v24 + v21;
    }
    else
    {
      v23 = v30 + 4 * v20;
    }
    *((_QWORD *)&v30 + 1) = v23;
LABEL_16:
    MatchedProperty = TdhpGetMatchedProperty(
                        a1,
                        (unsigned __int64)a5,
                        a6,
                        (__int64)a5,
                        (__int64)v18,
                        0,
                        (__int64)(v18 + 28),
                        v18[26],
                        (__int64)a8,
                        0,
                        a7,
                        a2,
                        v30,
                        &v28,
                        &v27,
                        (_DWORD *)v29 + 1);
    v19 = MatchedProperty;
    if ( MatchedProperty == 111 )
    {
      v19 = 15005;
    }
    else if ( !MatchedProperty )
    {
      *a9 = v27;
      *a10 = v28;
    }
    goto LABEL_20;
  }
  v19 = 1168;
LABEL_20:
  ReleaseSRWLockShared(v15);
  TdhpCacheFreeEntry(0, v15);
  if ( LODWORD(v29[0]) && v18 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v18);
  }
  if ( (_QWORD)v30 )
    std::_Deallocate<16>(v30, (v31 - v30) & 0xFFFFFFFFFFFFFFFCuLL);
  return v19;
}

```

## disassembly

```asm
0x1800270cc  mov     rax, rsp
0x1800270cf  mov     [rax+8], ecx
0x1800270d2  push    rbx
0x1800270d3  push    rsi
0x1800270d4  push    rdi
0x1800270d5  push    r13
0x1800270d7  push    r14
0x1800270d9  push    r15
0x1800270db  sub     rsp, 0C8h
0x1800270e2  mov     r14, r9
0x1800270e5  mov     rbx, r8
0x1800270e8  movzx   r13d, dx
0x1800270ec  mov     r15d, ecx
0x1800270ef  xor     edi, edi
0x1800270f1  mov     [rax-70h], edi
0x1800270f4  xorps   xmm0, xmm0
0x1800270f7  movdqu  xmmword ptr [rax-58h], xmm0
0x1800270fc  mov     [rax-48h], rdi
0x180027100  mov     [rax-74h], edi
0x180027103  mov     [rax-78h], edi
0x180027106  mov     [rax-6Ch], edi
0x180027109  cmp     [rsp+0F8h+arg_20], rdi
0x180027111  jz      loc_180027363
0x180027117  cmp     [rsp+0F8h+arg_28], edi
0x18002711e  jbe     loc_180027363
0x180027124  mov     rdx, rbx
0x180027127  xor     ecx, ecx
0x180027129  call    TdhpCacheLockEntry
0x18002712e  mov     rsi, rax
0x180027131  mov     [rsp+0F8h+var_68], rax
0x180027139  test    rax, rax
0x18002713c  jnz     short loc_180027169
0x18002713e  mov     rcx, [rsp+0F8h+var_58]
0x180027146  test    rcx, rcx
0x180027149  jz      short loc_18002715F
0x18002714b  mov     rdx, [rsp+0F8h+var_48]
0x180027153  sub     rdx, rcx
0x180027156  and     rdx, 0FFFFFFFFFFFFFFFCh
0x18002715a  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18002715f  mov     eax, 8
0x180027164  jmp     loc_180027368
0x180027169  mov     rcx, rsi; SRWLock
0x18002716c  call    cs:__imp_AcquireSRWLockShared
0x180027172  lea     rax, [rsp+0F8h+var_70]
0x18002717a  mov     [rsp+0F8h+var_C0], rax; __int64
0x18002717f  mov     [rsp+0F8h+var_C8], edi; int
0x180027183  mov     [rsp+0F8h+var_D0], rdi; __int64
0x180027188  mov     [rsp+0F8h+var_D8], r14; __int64
0x18002718d  mov     r9, rbx
0x180027190  mov     r8, rsi
0x180027193  movzx   edx, r13w
0x180027197  mov     ecx, r15d; unsigned int
0x18002719a  call    TdhpGetTraceEventInfoFromMofInfo
0x18002719f  mov     r14, rax
0x1800271a2  mov     [rsp+0F8h+var_60], rax
0x1800271aa  test    rax, rax
0x1800271ad  jnz     short loc_1800271B9
0x1800271af  mov     ebx, 490h
0x1800271b4  jmp     loc_180027308
0x1800271b9  mov     ebx, [rax+64h]
0x1800271bc  mov     rdx, [rsp+0F8h+var_58]
0x1800271c4  mov     r15, [rsp+0F8h+var_50]
0x1800271cc  mov     rcx, r15
0x1800271cf  sub     rcx, rdx
0x1800271d2  sar     rcx, 2
0x1800271d6  cmp     rbx, rcx
0x1800271d9  jnb     short loc_1800271E1
0x1800271db  lea     rax, [rdx+rbx*4]
0x1800271df  jmp     short loc_180027221
0x1800271e1  jbe     short loc_180027229
0x1800271e3  mov     rax, [rsp+0F8h+var_48]
0x1800271eb  sub     rax, rdx
0x1800271ee  sar     rax, 2
0x1800271f2  cmp     rbx, rax
0x1800271f5  jbe     short loc_180027209
0x1800271f7  mov     rdx, rbx
0x1800271fa  lea     rcx, [rsp+0F8h+var_58]
0x180027202  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@KV?$allocator@K@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<ulong>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x180027207  jmp     short loc_180027229
0x180027209  sub     rbx, rcx
0x18002720c  shl     rbx, 2
0x180027210  mov     r8, rbx; Size
0x180027213  xor     edx, edx; Val
0x180027215  mov     rcx, r15; void *
0x180027218  call    memset_0
0x18002721d  lea     rax, [rbx+r15]
0x180027221  mov     [rsp+0F8h+var_50], rax
0x180027229  mov     rax, [rsp+0F8h+var_58]
0x180027231  lea     rcx, [r14+70h]
0x180027235  lea     rdx, [rsp+0F8h+var_70+4]
0x18002723d  mov     [rsp+0F8h+var_80], rdx
0x180027242  lea     rdx, [rsp+0F8h+var_78]
0x18002724a  mov     [rsp+0F8h+var_88], rdx
0x18002724f  lea     rdx, [rsp+0F8h+var_74]
0x180027257  mov     [rsp+0F8h+var_90], rdx
0x18002725c  mov     [rsp+0F8h+var_98], rax
0x180027261  mov     [rsp+0F8h+var_A0], r13w
0x180027267  mov     eax, [rsp+0F8h+arg_30]
0x18002726e  mov     [rsp+0F8h+var_A8], eax
0x180027272  mov     [rsp+0F8h+var_B0], edi
0x180027276  mov     rax, [rsp+0F8h+arg_38]
0x18002727e  mov     [rsp+0F8h+var_B8], rax
0x180027283  mov     eax, [r14+68h]
0x180027287  mov     dword ptr [rsp+0F8h+var_C0], eax
0x18002728b  mov     qword ptr [rsp+0F8h+var_C8], rcx
0x180027290  mov     word ptr [rsp+0F8h+var_D0], di
0x180027295  mov     [rsp+0F8h+var_D8], r14
0x18002729a  mov     r9, [rsp+0F8h+arg_20]
0x1800272a2  mov     r8d, [rsp+0F8h+arg_28]
0x1800272aa  mov     rdx, r9
0x1800272ad  mov     ecx, [rsp+0F8h+arg_0]
0x1800272b4  call    TdhpGetMatchedProperty
0x1800272b9  mov     ebx, eax
0x1800272bb  cmp     eax, 6Fh ; 'o'
0x1800272be  jnz     short loc_1800272C7
0x1800272c0  mov     ebx, 3A9Dh
0x1800272c5  jmp     short loc_180027308
0x1800272c7  test    eax, eax
0x1800272c9  jnz     short loc_180027308
0x1800272cb  mov     rcx, [rsp+0F8h+arg_40]
0x1800272d3  mov     eax, [rsp+0F8h+var_78]
0x1800272da  mov     [rcx], eax
0x1800272dc  mov     rcx, [rsp+0F8h+arg_48]
0x1800272e4  mov     eax, [rsp+0F8h+var_74]
0x1800272eb  mov     [rcx], eax
0x1800272ed  jmp     short loc_180027308
0x1800272ef  xor     edi, edi
0x1800272f1  mov     ebx, dword ptr [rsp+0F8h+arg_20]
0x1800272f8  mov     rsi, [rsp+0F8h+var_68]
0x180027300  mov     r14, [rsp+0F8h+var_60]
0x180027308  mov     rcx, rsi; SRWLock
0x18002730b  call    cs:__imp_ReleaseSRWLockShared
0x180027311  mov     rdx, rsi
0x180027314  xor     ecx, ecx
0x180027316  call    TdhpCacheFreeEntry
0x18002731b  cmp     dword ptr [rsp+0F8h+var_70], edi
0x180027322  jz      short loc_18002733E
0x180027324  test    r14, r14
0x180027327  jz      short loc_18002733E
0x180027329  call    cs:__imp_GetProcessHeap
0x18002732f  mov     rcx, rax; hHeap
0x180027332  mov     r8, r14; lpMem
0x180027335  xor     edx, edx; dwFlags
0x180027337  call    cs:__imp_HeapFree
0x18002733d  nop
0x18002733e  mov     rcx, [rsp+0F8h+var_58]
0x180027346  test    rcx, rcx
0x180027349  jz      short loc_18002735F
0x18002734b  mov     rdx, [rsp+0F8h+var_48]
0x180027353  sub     rdx, rcx
0x180027356  and     rdx, 0FFFFFFFFFFFFFFFCh
0x18002735a  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18002735f  mov     eax, ebx
0x180027361  jmp     short loc_180027368
0x180027363  mov     eax, 0Dh
0x180027368  add     rsp, 0C8h
0x18002736f  pop     r15
0x180027371  pop     r14
0x180027373  pop     r13
0x180027375  pop     rdi
0x180027376  pop     rsi
0x180027377  pop     rbx
0x180027378  retn
```
