# PmkCacheSetParams(MSMSEC_PMKCACHE_CONTEXT *,MSMSEC_NW_DESC *,DOT11_MSMSEC_CONNECTION_PROFILE *,ulong,void *)

- ea: `0x1800367a8`
- end: `0x18003698a`
- name: `?PmkCacheSetParams@@YAKPEAUMSMSEC_PMKCACHE_CONTEXT@@PEAUMSMSEC_NW_DESC@@PEAUDOT11_MSMSEC_CONNECTION_PROFILE@@KPEAX@Z`
- size: `482`
- prototype: `unsigned int __usercall@<eax>(struct MSMSEC_PMKCACHE_CONTEXT *@<rcx>, struct MSMSEC_NW_DESC *@<rdx>, struct DOT11_MSMSEC_CONNECTION_PROFILE *@<r8>, unsigned int@<r9d>, void *)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x180037b68`
- `0x18006b788`

## callees

- `0x18000892c`
- `0x180008998`
- `0x18002ddd4`
- `0x180032408`
- `0x1800367a8`
- `0x18006bbd8`

## import_xrefs

- `OneX!OneXCopyAuthParams` at `0x18003680a`
- `OneX!OneXCopyAuthParams` at `0x18003680a`
- `OneX!OneXFreeAuthParams` at `0x18003685e`
- `OneX!OneXFreeAuthParams` at `0x1800368e8`
- `OneX!OneXFreeAuthParams` at `0x18003685e`
- `OneX!OneXFreeAuthParams` at `0x1800368e8`

## pseudocode

```c
__int64 __fastcall PmkCacheSetParams(
        struct MSMSEC_PMKCACHE_CONTEXT *a1,
        struct MSMSEC_NW_DESC *a2,
        struct DOT11_MSMSEC_CONNECTION_PROFILE *a3,
        unsigned int a4,
        void *a5)
{
  unsigned int v9; // eax
  unsigned int v10; // edi
  PVOID *v11; // rcx
  void *v13; // [rsp+20h] [rbp-48h] BYREF

  v13 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 121, &WPP_33279517f8f53e554228e3ed86a1217c_Traceguids);
  v9 = OneXCopyAuthParams(a4, a5, &v13);
  v10 = v9;
  if ( !v9 )
  {
    *((_OWORD *)a1 + 9) = 0;
    *((_OWORD *)a1 + 10) = 0;
    *((_DWORD *)a1 + 44) = 0;
    *(_OWORD *)((char *)a1 + 148) = *(_OWORD *)((char *)a2 + 4);
    *(_OWORD *)((char *)a1 + 164) = *(_OWORD *)((char *)a2 + 20);
    *((_DWORD *)a1 + 36) = *(_DWORD *)a2;
    *((_DWORD *)a1 + 45) = *((_DWORD *)a2 + 9);
    *((_DWORD *)a1 + 46) = **((_DWORD **)a3 + 3);
    *((_DWORD *)a1 + 47) = *(_DWORD *)(*((_QWORD *)a3 + 3) + 4LL);
    if ( (unsigned int)IsPMKAuthParamsAvailable(a1) )
    {
      OneXFreeAuthParams(*((_QWORD *)a1 + 25));
      *((_QWORD *)a1 + 25) = 0;
      *((_DWORD *)a1 + 48) = 0;
    }
    SetPMKAuthParams(a1, a4, v13);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 2) != 0 )
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 7), 34, &WPP_33279517f8f53e554228e3ed86a1217c_Traceguids, "INITIALIZED");
    *((_DWORD *)a1 + 1) = 1;
    goto LABEL_16;
  }
  v11 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 122, &WPP_33279517f8f53e554228e3ed86a1217c_Traceguids, v9);
    v11 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v13 )
  {
    OneXFreeAuthParams(v13);
    v13 = 0;
LABEL_16:
    v11 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v11 != &WPP_GLOBAL_Control && (*((_DWORD *)v11 + 17) & 0x100) != 0 )
    WPP_SF_d(v11[7], 123, &WPP_33279517f8f53e554228e3ed86a1217c_Traceguids, v10);
  return v10;
}

```

## disassembly

```asm
0x1800367a8  push    rbx
0x1800367aa  push    rbp
0x1800367ab  push    rsi
0x1800367ac  push    rdi
0x1800367ad  push    r12
0x1800367af  push    r14
0x1800367b1  sub     rsp, 38h
0x1800367b5  mov     esi, r9d
0x1800367b8  mov     [rsp+68h+var_48], 0
0x1800367c1  mov     rbp, r8
0x1800367c4  mov     r14, rdx
0x1800367c7  mov     rbx, rcx
0x1800367ca  mov     rcx, cs:WPP_GLOBAL_Control
0x1800367d1  lea     r12, WPP_GLOBAL_Control
0x1800367d8  cmp     rcx, r12
0x1800367db  jz      short loc_1800367FB
0x1800367dd  test    dword ptr [rcx+44h], 100h
0x1800367e4  jz      short loc_1800367FB
0x1800367e6  mov     rcx, [rcx+38h]
0x1800367ea  lea     r8, WPP_33279517f8f53e554228e3ed86a1217c_Traceguids
0x1800367f1  mov     edx, 79h ; 'y'
0x1800367f6  call    WPP_SF_
0x1800367fb  mov     rdx, [rsp+68h+arg_20]
0x180036803  lea     r8, [rsp+68h+var_48]
0x180036808  mov     ecx, esi
0x18003680a  call    cs:__imp_OneXCopyAuthParams
0x180036811  nop     dword ptr [rax+rax+00h]
0x180036816  mov     edi, eax
0x180036818  test    eax, eax
0x18003681a  jz      short loc_180036878
0x18003681c  mov     rcx, cs:WPP_GLOBAL_Control
0x180036823  cmp     rcx, r12
0x180036826  jz      short loc_18003684D
0x180036828  test    byte ptr [rcx+44h], 1
0x18003682c  jz      short loc_18003684D
0x18003682e  mov     rcx, [rcx+38h]
0x180036832  lea     r8, WPP_33279517f8f53e554228e3ed86a1217c_Traceguids
0x180036839  mov     edx, 7Ah ; 'z'
0x18003683e  mov     r9d, eax
0x180036841  call    WPP_SF_d
0x180036846  mov     rcx, cs:WPP_GLOBAL_Control
0x18003684d  mov     rax, [rsp+68h+var_48]
0x180036852  test    rax, rax
0x180036855  jz      loc_180036954
0x18003685b  mov     rcx, rax
0x18003685e  call    cs:__imp_OneXFreeAuthParams
0x180036865  nop     dword ptr [rax+rax+00h]
0x18003686a  mov     [rsp+68h+var_48], 0
0x180036873  jmp     loc_18003694D
0x180036878  xor     eax, eax
0x18003687a  xorps   xmm0, xmm0
0x18003687d  movups  xmmword ptr [rbx+90h], xmm0
0x180036884  movups  xmmword ptr [rbx+0A0h], xmm0
0x18003688b  mov     [rbx+0B0h], eax
0x180036891  movups  xmm0, xmmword ptr [r14+4]
0x180036896  movups  xmmword ptr [rbx+94h], xmm0
0x18003689d  movups  xmm1, xmmword ptr [r14+14h]
0x1800368a2  movups  xmmword ptr [rbx+0A4h], xmm1
0x1800368a9  mov     eax, [r14]
0x1800368ac  mov     [rbx+90h], eax
0x1800368b2  mov     eax, [r14+24h]
0x1800368b6  mov     [rbx+0B4h], eax
0x1800368bc  mov     rax, [rbp+18h]
0x1800368c0  mov     ecx, [rax]
0x1800368c2  mov     [rbx+0B8h], ecx
0x1800368c8  mov     rax, [rbp+18h]
0x1800368cc  mov     ecx, [rax+4]
0x1800368cf  mov     [rbx+0BCh], ecx
0x1800368d5  mov     rcx, rbx; struct MSMSEC_PMKCACHE_CONTEXT *
0x1800368d8  call    ?IsPMKAuthParamsAvailable@@YAHPEAUMSMSEC_PMKCACHE_CONTEXT@@@Z; IsPMKAuthParamsAvailable(MSMSEC_PMKCACHE_CONTEXT *)
0x1800368dd  test    eax, eax
0x1800368df  jz      short loc_180036909
0x1800368e1  mov     rcx, [rbx+0C8h]
0x1800368e8  call    cs:__imp_OneXFreeAuthParams
0x1800368ef  nop     dword ptr [rax+rax+00h]
0x1800368f4  mov     qword ptr [rbx+0C8h], 0
0x1800368ff  mov     dword ptr [rbx+0C0h], 0
0x180036909  mov     r8, [rsp+68h+var_48]; void *
0x18003690e  mov     edx, esi; unsigned int
0x180036910  mov     rcx, rbx; struct MSMSEC_PMKCACHE_CONTEXT *
0x180036913  call    ?SetPMKAuthParams@@YAXPEAUMSMSEC_PMKCACHE_CONTEXT@@KPEAX@Z; SetPMKAuthParams(MSMSEC_PMKCACHE_CONTEXT *,ulong,void *)
0x180036918  mov     rcx, cs:WPP_GLOBAL_Control
0x18003691f  cmp     rcx, r12
0x180036922  jz      short loc_180036946
0x180036924  test    byte ptr [rcx+44h], 2
0x180036928  jz      short loc_180036946
0x18003692a  mov     rcx, [rcx+38h]
0x18003692e  lea     r9, aInitialized_0; "INITIALIZED"
0x180036935  mov     edx, 22h ; '"'
0x18003693a  lea     r8, WPP_33279517f8f53e554228e3ed86a1217c_Traceguids
0x180036941  call    WPP_SF_s
0x180036946  mov     dword ptr [rbx+4], 1
0x18003694d  mov     rcx, cs:WPP_GLOBAL_Control
0x180036954  cmp     rcx, r12
0x180036957  jz      short loc_18003697A
0x180036959  test    dword ptr [rcx+44h], 100h
0x180036960  jz      short loc_18003697A
0x180036962  mov     rcx, [rcx+38h]
0x180036966  lea     r8, WPP_33279517f8f53e554228e3ed86a1217c_Traceguids
0x18003696d  mov     edx, 7Bh ; '{'
0x180036972  mov     r9d, edi
0x180036975  call    WPP_SF_d
0x18003697a  mov     eax, edi
0x18003697c  add     rsp, 38h
0x180036980  pop     r14
0x180036982  pop     r12
0x180036984  pop     rdi
0x180036985  pop     rsi
0x180036986  pop     rbp
0x180036987  pop     rbx
0x180036988  retn
```
