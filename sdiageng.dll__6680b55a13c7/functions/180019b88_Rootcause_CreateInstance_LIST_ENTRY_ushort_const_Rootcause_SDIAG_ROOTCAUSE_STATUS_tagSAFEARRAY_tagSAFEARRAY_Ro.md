# Rootcause::CreateInstance(_LIST_ENTRY *,ushort const *,Rootcause::SDIAG_ROOTCAUSE_STATUS,tagSAFEARRAY *,tagSAFEARRAY *,Rootcause::_SDIAG_ROOTCAUSE_INSTANCE * *)

- ea: `0x180019b88`
- end: `0x180019d81`
- name: `?CreateInstance@Rootcause@@AEAAJPEAU_LIST_ENTRY@@PEBGW4SDIAG_ROOTCAUSE_STATUS@1@PEAUtagSAFEARRAY@@3PEAPEAU_SDIAG_ROOTCAUSE_INSTANCE@1@@Z`
- size: `505`
- prototype: `__int64 __fastcall(__int64, struct IXMLDOMDocument2 *, __int64, unsigned int, __int64, __int64, struct IXMLDOMDocument2 ***)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180018718`
- `0x18001aaf0`

## callees

- `0x1800012b0`
- `0x180019b88`
- `0x180019d88`
- `0x18001aa50`
- `0x180026fa0`
- `0x1800280f8`
- `0x180029882`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x180019bf8`
- `KERNEL32!HeapAlloc` at `0x180019bf8`
- `KERNEL32!GetProcessHeap` at `0x180019be4`
- `KERNEL32!GetProcessHeap` at `0x180019d47`
- `KERNEL32!GetProcessHeap` at `0x180019be4`
- `KERNEL32!GetProcessHeap` at `0x180019d47`
- `KERNEL32!HeapFree` at `0x180019d55`
- `KERNEL32!HeapFree` at `0x180019d55`

## string_xrefs

- `0x180019c63`: `<?xml version="1.0" encoding="utf-8"?><DetailedInformation/>`
- `0x180019ce3`: `<?xml version="1.0" encoding="utf-8"?><DetailedInformation/>`
- `0x180019bb6`: `Rootcause::CreateInstance`
- `0x180019d31`: `Rootcause::CreateInstance`

## pseudocode

```c
__int64 __fastcall Rootcause::CreateInstance(
        __int64 a1,
        struct IXMLDOMDocument2 *a2,
        __int64 a3,
        unsigned int a4,
        __int64 a5,
        __int64 a6,
        struct IXMLDOMDocument2 ***a7)
{
  int v11; // r8d
  int v12; // r9d
  unsigned int v13; // esi
  HANDLE ProcessHeap; // rax
  struct IXMLDOMDocument2 **v15; // rax
  struct IXMLDOMDocument2 **v16; // rdi
  __int64 v17; // rcx
  int v18; // eax
  int v19; // r8d
  int v20; // r9d
  struct IXMLDOMDocument2 *v21; // rax
  unsigned int v22; // r14d
  __int64 v23; // r12
  struct IXMLDOMDocument2 ***lpVtbl; // rax
  Rootcause *v25; // rcx
  HANDLE v26; // rax

  if ( !a3 )
  {
    v11 = 2090;
LABEL_3:
    v12 = -2147024809;
LABEL_4:
    v13 = v12;
    SdpDebugTrace(1u, L"Rootcause::CreateInstance", v11, v12);
    return v13;
  }
  if ( !a7 )
  {
    v11 = 2091;
    goto LABEL_3;
  }
  ProcessHeap = GetProcessHeap();
  v15 = (struct IXMLDOMDocument2 **)HeapAlloc(ProcessHeap, 0, 0x48u);
  v16 = v15;
  if ( !v15 )
  {
    v12 = -2147024882;
    v11 = 2096;
    goto LABEL_4;
  }
  memset_0(v15, 0, 0x48u);
  v18 = Rootcause::PopulateInstance(v17, a3, a4, a5, a6, v16);
  v13 = v18;
  if ( v18 < 0 )
  {
    v19 = 2101;
LABEL_11:
    v20 = v18;
LABEL_22:
    SdpDebugTrace(1u, L"Rootcause::CreateInstance", v19, v20);
    Rootcause::FreeInstance(v25, (struct Rootcause::_SDIAG_ROOTCAUSE_INSTANCE *)v16);
    v26 = GetProcessHeap();
    HeapFree(v26, 0, v16);
    return v13;
  }
  v18 = SdpXmlCreate((OLECHAR *)L"<?xml version=\"1.0\" encoding=\"utf-8\"?><DetailedInformation/>", v16 + 6);
  v13 = v18;
  if ( v18 < 0 )
  {
    v19 = 2105;
    goto LABEL_11;
  }
  v21 = (struct IXMLDOMDocument2 *)operator new[](saturated_mul(*(unsigned int *)(a1 + 32), 0x10u));
  v16[7] = v21;
  if ( !v21 )
  {
    v20 = -2147024882;
    v13 = -2147024882;
    v19 = 2108;
    goto LABEL_22;
  }
  memset_0(v21, 0, 16LL * *(unsigned int *)(a1 + 32));
  v22 = 0;
  *((_DWORD *)v16 + 16) = *(_DWORD *)(a1 + 32);
  if ( *(_DWORD *)(a1 + 32) )
  {
    while ( 1 )
    {
      v23 = 2LL * v22;
      v13 = SdpXmlCreate(
              (OLECHAR *)L"<?xml version=\"1.0\" encoding=\"utf-8\"?><DetailedInformation/>",
              (struct IXMLDOMDocument2 **)&v16[7][v23 + 1]);
      v20 = v13;
      if ( (v13 & 0x80000000) != 0 )
        break;
      ++v22;
      LODWORD(v16[7][v23].lpVtbl) = 0;
      if ( v22 >= *(_DWORD *)(a1 + 32) )
        goto LABEL_19;
    }
    v19 = 2116;
    goto LABEL_22;
  }
LABEL_19:
  lpVtbl = (struct IXMLDOMDocument2 ***)a2[1].lpVtbl;
  if ( *lpVtbl != (struct IXMLDOMDocument2 **)a2 )
    __fastfail(3u);
  *v16 = a2;
  v16[1] = (struct IXMLDOMDocument2 *)lpVtbl;
  *lpVtbl = v16;
  a2[1].lpVtbl = (struct IXMLDOMDocument2Vtbl *)v16;
  *a7 = v16;
  return v13;
}

```

## disassembly

```asm
0x180019b88  push    rbx
0x180019b8a  push    rbp
0x180019b8b  push    rsi
0x180019b8c  push    rdi
0x180019b8d  push    r12
0x180019b8f  push    r13
0x180019b91  push    r14
0x180019b93  push    r15
0x180019b95  sub     rsp, 38h
0x180019b99  mov     esi, r9d
0x180019b9c  mov     rbx, r8
0x180019b9f  mov     rbp, rdx
0x180019ba2  mov     r13, rcx
0x180019ba5  test    r8, r8
0x180019ba8  jnz     short loc_180019BCF
0x180019baa  mov     r8d, 82Ah; int
0x180019bb0  mov     r9d, 80070057h; int
0x180019bb6  lea     rdx, aRootcauseCreat; "Rootcause::CreateInstance"
0x180019bbd  mov     ecx, 1; Level
0x180019bc2  mov     esi, r9d
0x180019bc5  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180019bca  jmp     loc_180019D6E
0x180019bcf  mov     r15, [rsp+78h+arg_30]
0x180019bd7  test    r15, r15
0x180019bda  jnz     short loc_180019BE4
0x180019bdc  mov     r8d, 82Bh
0x180019be2  jmp     short loc_180019BB0
0x180019be4  call    cs:__imp_GetProcessHeap
0x180019bea  mov     r14d, 48h ; 'H'
0x180019bf0  xor     edx, edx; dwFlags
0x180019bf2  mov     rcx, rax; hHeap
0x180019bf5  mov     r8d, r14d; dwBytes
0x180019bf8  call    cs:__imp_HeapAlloc
0x180019bfe  mov     rdi, rax
0x180019c01  test    rax, rax
0x180019c04  jnz     short loc_180019C14
0x180019c06  mov     r9d, 8007000Eh
0x180019c0c  mov     r8d, 830h
0x180019c12  jmp     short loc_180019BB6
0x180019c14  mov     r8, r14; Size
0x180019c17  xor     edx, edx; Val
0x180019c19  mov     rcx, rdi; void *
0x180019c1c  call    memset_0
0x180019c21  mov     rax, [rsp+78h+arg_28]
0x180019c29  mov     r8d, esi
0x180019c2c  mov     r9, [rsp+78h+arg_20]
0x180019c34  mov     rdx, rbx
0x180019c37  mov     [rsp+78h+var_50], rdi
0x180019c3c  mov     [rsp+78h+var_58], rax
0x180019c41  call    ?PopulateInstance@Rootcause@@AEAAJPEBGW4SDIAG_ROOTCAUSE_STATUS@1@PEAUtagSAFEARRAY@@2PEAU_SDIAG_ROOTCAUSE_INSTANCE@1@@Z; Rootcause::PopulateInstance(ushort const *,Rootcause::SDIAG_ROOTCAUSE_STATUS,tagSAFEARRAY *,tagSAFEARRAY *,Rootcause::_SDIAG_ROOTCAUSE_INSTANCE *)
0x180019c46  mov     esi, eax
0x180019c48  test    eax, eax
0x180019c4a  jns     short loc_180019C5F
0x180019c4c  mov     r8d, 835h
0x180019c52  mov     ebx, 1
0x180019c57  mov     r9d, eax
0x180019c5a  jmp     loc_180019D31
0x180019c5f  lea     rdx, [rdi+30h]; struct IXMLDOMDocument2 **
0x180019c63  lea     rcx, aXmlVersion10En_20; "<?xml version=\"1.0\" encoding=\"utf-8"...
0x180019c6a  call    ?SdpXmlCreate@@YAJPEBGPEAPEAUIXMLDOMDocument2@@@Z; SdpXmlCreate(ushort const *,IXMLDOMDocument2 * *)
0x180019c6f  mov     esi, eax
0x180019c71  test    eax, eax
0x180019c73  jns     short loc_180019C7D
0x180019c75  mov     r8d, 839h
0x180019c7b  jmp     short loc_180019C52
0x180019c7d  mov     ecx, [r13+20h]
0x180019c81  mov     eax, 10h
0x180019c86  mul     rcx
0x180019c89  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180019c90  cmovb   rax, rcx
0x180019c94  mov     rcx, rax; unsigned __int64
0x180019c97  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180019c9c  mov     [rdi+38h], rax
0x180019ca0  test    rax, rax
0x180019ca3  jnz     short loc_180019CB9
0x180019ca5  mov     r9d, 8007000Eh
0x180019cab  lea     ebx, [rax+1]
0x180019cae  mov     esi, r9d
0x180019cb1  mov     r8d, 83Ch
0x180019cb7  jmp     short loc_180019D31
0x180019cb9  mov     r8d, [r13+20h]
0x180019cbd  xor     edx, edx; Val
0x180019cbf  shl     r8, 4; Size
0x180019cc3  mov     rcx, rax; void *
0x180019cc6  call    memset_0
0x180019ccb  mov     eax, [r13+20h]
0x180019ccf  xor     r14d, r14d
0x180019cd2  mov     [rdi+40h], eax
0x180019cd5  cmp     [r13+20h], r14d
0x180019cd9  jbe     short loc_180019D1B
0x180019cdb  lea     ebx, [r14+1]
0x180019cdf  mov     rdx, [rdi+38h]
0x180019ce3  lea     rcx, aXmlVersion10En_20; "<?xml version=\"1.0\" encoding=\"utf-8"...
0x180019cea  add     rdx, 8
0x180019cee  mov     r12d, r14d
0x180019cf1  shl     r12, 4
0x180019cf5  add     rdx, r12; struct IXMLDOMDocument2 **
0x180019cf8  call    ?SdpXmlCreate@@YAJPEBGPEAPEAUIXMLDOMDocument2@@@Z; SdpXmlCreate(ushort const *,IXMLDOMDocument2 * *)
0x180019cfd  mov     esi, eax
0x180019cff  mov     r9d, eax; int
0x180019d02  test    eax, eax
0x180019d04  js      short loc_180019D2B
0x180019d06  mov     rax, [rdi+38h]
0x180019d0a  add     r14d, ebx
0x180019d0d  mov     dword ptr [r12+rax], 0
0x180019d15  cmp     r14d, [r13+20h]
0x180019d19  jb      short loc_180019CDF
0x180019d1b  mov     rax, [rbp+8]
0x180019d1f  cmp     [rax], rbp
0x180019d22  jz      short loc_180019D5D
0x180019d24  mov     ecx, 3
0x180019d29  int     29h; Win8: RtlFailFast(ecx)
0x180019d2b  mov     r8d, 844h; int
0x180019d31  lea     rdx, aRootcauseCreat; "Rootcause::CreateInstance"
0x180019d38  mov     ecx, ebx; Level
0x180019d3a  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180019d3f  mov     rdx, rdi; struct Rootcause::_SDIAG_ROOTCAUSE_INSTANCE *
0x180019d42  call    ?FreeInstance@Rootcause@@AEAAJPEAU_SDIAG_ROOTCAUSE_INSTANCE@1@@Z; Rootcause::FreeInstance(Rootcause::_SDIAG_ROOTCAUSE_INSTANCE *)
0x180019d47  call    cs:__imp_GetProcessHeap
0x180019d4d  mov     r8, rdi; lpMem
0x180019d50  xor     edx, edx; dwFlags
0x180019d52  mov     rcx, rax; hHeap
0x180019d55  call    cs:__imp_HeapFree
0x180019d5b  jmp     short loc_180019D6E
0x180019d5d  mov     [rdi], rbp
0x180019d60  mov     [rdi+8], rax
0x180019d64  mov     [rax], rdi
0x180019d67  mov     [rbp+8], rdi
0x180019d6b  mov     [r15], rdi
0x180019d6e  mov     eax, esi
0x180019d70  add     rsp, 38h
0x180019d74  pop     r15
0x180019d76  pop     r14
0x180019d78  pop     r13
0x180019d7a  pop     r12
0x180019d7c  pop     rdi
0x180019d7d  pop     rsi
0x180019d7e  pop     rbp
0x180019d7f  pop     rbx
0x180019d80  retn
```
