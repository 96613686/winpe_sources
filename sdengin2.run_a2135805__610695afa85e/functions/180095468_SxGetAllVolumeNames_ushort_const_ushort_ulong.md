# SxGetAllVolumeNames(ushort const *,ushort * * *,ulong *)

- ea: `0x180095468`
- end: `0x180095800`
- name: `?SxGetAllVolumeNames@@YAJPEBGPEAPEAPEAGPEAK@Z`
- size: `920`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 ***, unsigned int *)`
- caller_count: `1`
- callee_count: `11`
- tags: `service_task`

## callers

- `0x18004bfd0`

## callees

- `0x1800083e4`
- `0x180014eac`
- `0x180072e08`
- `0x180072f14`
- `0x180092cb0`
- `0x180094074`
- `0x180094130`
- `0x1800941a8`
- `0x180094670`
- `0x180094d48`
- `0x180095468`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18009560a`
- `KERNEL32!GetLastError` at `0x18009560a`
- `KERNEL32!GetVolumePathNamesForVolumeNameW` at `0x1800955f6`
- `KERNEL32!GetVolumePathNamesForVolumeNameW` at `0x1800955f6`
- `ole32!CoTaskMemFree` at `0x18009573e`
- `ole32!CoTaskMemFree` at `0x18009574d`
- `ole32!CoTaskMemFree` at `0x180095771`
- `ole32!CoTaskMemFree` at `0x1800957a4`
- `ole32!CoTaskMemFree` at `0x1800957c3`
- `ole32!CoTaskMemFree` at `0x18009573e`
- `ole32!CoTaskMemFree` at `0x18009574d`
- `ole32!CoTaskMemFree` at `0x180095771`
- `ole32!CoTaskMemFree` at `0x1800957a4`
- `ole32!CoTaskMemFree` at `0x1800957c3`
- `ole32!CoTaskMemRealloc` at `0x1800955c3`
- `ole32!CoTaskMemRealloc` at `0x1800955c3`

## pseudocode

```c
__int64 __fastcall SxGetAllVolumeNames(const unsigned __int16 *a1, unsigned __int16 ***a2, unsigned int *a3)
{
  void *v6; // r12
  void *v7; // rdi
  unsigned __int16 *v8; // rsi
  __int16 v9; // ax
  int AllVolumeGUIDNames; // eax
  bool v11; // sf
  const WCHAR *v12; // rbx
  DWORD v13; // eax
  signed int LastError; // eax
  const unsigned __int16 *i; // rbx
  int v16; // eax
  __int64 v17; // rax
  void *v18; // rcx
  unsigned __int16 **v19; // rax
  unsigned int j; // esi
  __int64 v21; // rbx
  LPVOID *v22; // rcx
  unsigned int k; // esi
  __int64 v24; // rbx
  unsigned int v25; // ebx
  unsigned __int16 *v27; // [rsp+30h] [rbp-48h] BYREF
  int v28; // [rsp+38h] [rbp-40h] BYREF
  __int16 v29; // [rsp+3Ch] [rbp-3Ch]
  __int16 v30; // [rsp+3Eh] [rbp-3Ah]
  DWORD cchReturnLength; // [rsp+C0h] [rbp+48h] BYREF
  unsigned int v32; // [rsp+C8h] [rbp+50h] BYREF
  LPVOID pv; // [rsp+D0h] [rbp+58h] BYREF
  void *Block; // [rsp+D8h] [rbp+60h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_05ac73db944e38c734cd0ea2eac4b7ce_Traceguids, a1);
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v28, "SxGetAllVolumeNames", 0x191u, 1u);
  cchReturnLength = 0;
  v6 = 0;
  Block = 0;
  v7 = 0;
  v27 = 0;
  v8 = 0;
  pv = 0;
  v32 = 0;
  if ( a2 )
    *a2 = 0;
  if ( a3 )
    *a3 = 0;
  v9 = 418;
  if ( !a1 || (v29 = 418, v9 = 419, !a2) || (v29 = 419, v9 = 420, !a3) )
  {
    v28 = -2147024809;
    goto LABEL_38;
  }
  v28 = 0;
  v29 = 420;
  v28 = CSxSimpleArray<unsigned short *>::CreateInstance(&Block);
  v9 = 422;
  if ( v28 < 0 )
  {
    v7 = Block;
LABEL_38:
    v30 = v9;
    goto LABEL_39;
  }
  v29 = 422;
  AllVolumeGUIDNames = SxGetAllVolumeGUIDNames(a1, (unsigned __int16 ***)&pv, &v32);
  v7 = Block;
  v11 = AllVolumeGUIDNames < 0;
  v28 = AllVolumeGUIDNames;
  v9 = 427;
  if ( v11 )
    goto LABEL_38;
  v29 = 427;
  v28 = CSxSimpleArray<unsigned short *>::Attach(Block, v32, &pv);
  v9 = 428;
  if ( v28 < 0 )
    goto LABEL_38;
  v29 = 428;
  v12 = (const WCHAR *)**((_QWORD **)v7 + 1);
  v13 = 261;
  for ( cchReturnLength = 261; ; v13 = cchReturnLength )
  {
    v6 = CoTaskMemRealloc(v6, 2LL * v13);
    v9 = 443;
    if ( !v6 )
    {
      v28 = -2147024882;
      goto LABEL_38;
    }
    v28 = 0;
    v29 = 443;
    if ( GetVolumePathNamesForVolumeNameW(v12, (LPWCH)v6, cchReturnLength, &cchReturnLength) )
      break;
    LastError = GetLastError();
    if ( LastError == 122 || LastError == 234 )
    {
      LastError = 0;
    }
    else if ( LastError > 0 )
    {
      LastError = (unsigned __int16)LastError | 0x80070000;
    }
    v28 = LastError;
    if ( LastError < 0 )
    {
      v30 = 453;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000000) != 0 )
        WPP_SF_sSd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          17,
          (unsigned int)WPP_05ac73db944e38c734cd0ea2eac4b7ce_Traceguids,
          (unsigned int)"dwErr",
          (__int64)v12,
          LastError);
      goto LABEL_39;
    }
    v29 = 453;
  }
  for ( i = (const unsigned __int16 *)v6; *i; i += v17 + 1 )
  {
    v16 = SxCopyString(i, &v27);
    v8 = v27;
    v11 = v16 < 0;
    v28 = v16;
    v9 = 463;
    if ( v11 )
      goto LABEL_38;
    v29 = 463;
    v28 = CSxSimpleArray<unsigned short *>::Append(v7, v27);
    v9 = 464;
    if ( v28 < 0 )
      goto LABEL_38;
    v29 = 464;
    v8 = 0;
    v17 = -1;
    v27 = 0;
    do
      ++v17;
    while ( i[v17] );
  }
  v18 = v7;
  *a3 = *((_DWORD *)v7 + 4);
  v19 = (unsigned __int16 **)*((_QWORD *)v7 + 1);
  *((_QWORD *)v7 + 1) = 0;
  *((_QWORD *)v7 + 2) = 0;
  v7 = 0;
  *a2 = v19;
  CSxSimpleArray<unsigned short *>::Release(v18);
LABEL_39:
  CoTaskMemFree(v6);
  CoTaskMemFree(v8);
  if ( v7 )
  {
    for ( j = 0; j < *((_DWORD *)v7 + 4); *(_QWORD *)(*((_QWORD *)v7 + 1) + 8 * v21) = 0 )
    {
      v21 = j;
      CoTaskMemFree(*(LPVOID *)(*((_QWORD *)v7 + 1) + 8LL * j++));
    }
  }
  v22 = (LPVOID *)pv;
  if ( pv )
  {
    for ( k = 0; k < v32; v22 = (LPVOID *)pv )
    {
      v24 = k;
      CoTaskMemFree(v22[k++]);
      *((_QWORD *)pv + v24) = 0;
    }
    CoTaskMemFree(v22);
    pv = 0;
  }
  v25 = v28;
  if ( v7 )
    CSxSimpleArray<unsigned short *>::Release(v7);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v28);
  return v25;
}

```

## disassembly

```asm
0x180095468  push    rbp
0x18009546a  push    rbx
0x18009546b  push    rsi
0x18009546c  push    rdi
0x18009546d  push    r12
0x18009546f  push    r13
0x180095471  push    r14
0x180095473  push    r15
0x180095475  mov     rbp, rsp
0x180095478  sub     rsp, 78h
0x18009547c  mov     r14, r8
0x18009547f  mov     r15, rdx
0x180095482  mov     rbx, rcx
0x180095485  mov     rcx, cs:WPP_GLOBAL_Control
0x18009548c  lea     rax, WPP_GLOBAL_Control
0x180095493  cmp     rcx, rax
0x180095496  jz      short loc_1800954B9
0x180095498  test    dword ptr [rcx+1Ch], 20000000h
0x18009549f  jz      short loc_1800954B9
0x1800954a1  mov     rcx, [rcx+10h]
0x1800954a5  lea     r8, WPP_05ac73db944e38c734cd0ea2eac4b7ce_Traceguids
0x1800954ac  mov     edx, 10h
0x1800954b1  mov     r9, rbx
0x1800954b4  call    WPP_SF_S
0x1800954b9  mov     r9d, 1; unsigned __int16
0x1800954bf  lea     rdx, aSxgetallvolume_0; "SxGetAllVolumeNames"
0x1800954c6  mov     r8d, 191h; unsigned __int16
0x1800954cc  lea     rcx, [rbp+var_40]; this
0x1800954d0  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x1800954d5  xor     r13d, r13d
0x1800954d8  mov     [rbp+cchReturnLength], r13d
0x1800954dc  mov     r12d, r13d
0x1800954df  mov     [rbp+Block], r13
0x1800954e3  mov     edi, r13d
0x1800954e6  mov     [rbp+var_48], r13
0x1800954ea  mov     esi, r13d
0x1800954ed  mov     [rbp+pv], r13
0x1800954f1  mov     [rbp+arg_8], r13d
0x1800954f5  test    r15, r15
0x1800954f8  jz      short loc_1800954FD
0x1800954fa  mov     [r15], r13
0x1800954fd  test    r14, r14
0x180095500  jz      short loc_180095505
0x180095502  mov     [r14], r13d
0x180095505  mov     eax, 1A2h
0x18009550a  test    rbx, rbx
0x18009550d  jz      loc_180095730
0x180095513  mov     [rbp+var_3C], ax
0x180095517  mov     eax, 1A3h
0x18009551c  test    r15, r15
0x18009551f  jz      loc_180095730
0x180095525  mov     [rbp+var_3C], ax
0x180095529  mov     eax, 1A4h
0x18009552e  test    r14, r14
0x180095531  jz      loc_180095730
0x180095537  lea     rcx, [rbp+Block]
0x18009553b  mov     [rbp+var_40], r13d
0x18009553f  mov     [rbp+var_3C], ax
0x180095543  call    ?CreateInstance@?$CSxSimpleArray@PEAG@@SAJPEAPEAV1@@Z; CSxSimpleArray<ushort *>::CreateInstance(CSxSimpleArray<ushort *> * *)
0x180095548  mov     [rbp+var_40], eax
0x18009554b  test    eax, eax
0x18009554d  mov     eax, 1A6h
0x180095552  jns     short loc_18009555D
0x180095554  mov     rdi, [rbp+Block]
0x180095558  jmp     loc_180095737
0x18009555d  lea     r8, [rbp+arg_8]; unsigned int *
0x180095561  mov     [rbp+var_3C], ax
0x180095565  lea     rdx, [rbp+pv]; unsigned __int16 ***
0x180095569  mov     rcx, rbx; unsigned __int16 *
0x18009556c  call    ?SxGetAllVolumeGUIDNames@@YAJPEBGPEAPEAPEAGPEAK@Z; SxGetAllVolumeGUIDNames(ushort const *,ushort * * *,ulong *)
0x180095571  mov     rdi, [rbp+Block]
0x180095575  test    eax, eax
0x180095577  mov     [rbp+var_40], eax
0x18009557a  mov     eax, 1ABh
0x18009557f  js      loc_180095737
0x180095585  mov     edx, [rbp+arg_8]
0x180095588  lea     r8, [rbp+pv]
0x18009558c  mov     rcx, rdi
0x18009558f  mov     [rbp+var_3C], ax
0x180095593  call    ?Attach@?$CSxSimpleArray@PEAG@@QEAAJKPEAPEAPEAG@Z; CSxSimpleArray<ushort *>::Attach(ulong,ushort * * *)
0x180095598  mov     [rbp+var_40], eax
0x18009559b  test    eax, eax
0x18009559d  mov     eax, 1ACh
0x1800955a2  js      loc_180095737
0x1800955a8  mov     [rbp+var_3C], ax
0x1800955ac  mov     rax, [rdi+8]
0x1800955b0  mov     rbx, [rax]
0x1800955b3  mov     eax, 105h
0x1800955b8  mov     [rbp+cchReturnLength], eax
0x1800955bb  mov     edx, eax
0x1800955bd  mov     rcx, r12; pv
0x1800955c0  add     rdx, rdx; cb
0x1800955c3  call    cs:__imp_CoTaskMemRealloc
0x1800955ca  nop     dword ptr [rax+rax+00h]
0x1800955cf  mov     r12, rax
0x1800955d2  test    rax, rax
0x1800955d5  mov     eax, 1BBh
0x1800955da  jz      loc_180095727
0x1800955e0  mov     r8d, [rbp+cchReturnLength]; cchBufferLength
0x1800955e4  lea     r9, [rbp+cchReturnLength]; lpcchReturnLength
0x1800955e8  mov     rdx, r12; lpszVolumePathNames
0x1800955eb  mov     [rbp+var_40], r13d
0x1800955ef  mov     rcx, rbx; lpszVolumeName
0x1800955f2  mov     [rbp+var_3C], ax
0x1800955f6  call    cs:__imp_GetVolumePathNamesForVolumeNameW
0x1800955fd  nop     dword ptr [rax+rax+00h]
0x180095602  test    eax, eax
0x180095604  jnz     loc_1800956A2
0x18009560a  call    cs:__imp_GetLastError
0x180095611  nop     dword ptr [rax+rax+00h]
0x180095616  cmp     eax, 7Ah ; 'z'
0x180095619  jz      short loc_180095630
0x18009561b  cmp     eax, 0EAh
0x180095620  jz      short loc_180095630
0x180095622  test    eax, eax
0x180095624  jle     short loc_180095633
0x180095626  movzx   eax, ax
0x180095629  or      eax, 80070000h
0x18009562e  jmp     short loc_180095633
0x180095630  mov     eax, r13d
0x180095633  mov     [rbp+var_40], eax
0x180095636  test    eax, eax
0x180095638  js      short loc_18009564B
0x18009563a  mov     eax, 1C5h
0x18009563f  mov     [rbp+var_3C], ax
0x180095643  mov     eax, [rbp+cchReturnLength]
0x180095646  jmp     loc_1800955BB
0x18009564b  mov     ecx, 1C5h
0x180095650  mov     [rbp+var_3A], cx
0x180095654  mov     rcx, cs:WPP_GLOBAL_Control
0x18009565b  lea     rdx, WPP_GLOBAL_Control
0x180095662  cmp     rcx, rdx
0x180095665  jz      loc_18009573B
0x18009566b  test    dword ptr [rcx+1Ch], 2000000h
0x180095672  jz      loc_18009573B
0x180095678  mov     rcx, [rcx+10h]
0x18009567c  lea     r9, aDwerr; "dwErr"
0x180095683  mov     [rsp+78h+var_50], eax
0x180095687  lea     r8, WPP_05ac73db944e38c734cd0ea2eac4b7ce_Traceguids
0x18009568e  mov     edx, 11h
0x180095693  mov     [rsp+78h+var_58], rbx
0x180095698  call    WPP_SF_sSd
0x18009569d  jmp     loc_18009573B
0x1800956a2  mov     rbx, r12
0x1800956a5  cmp     [rbx], r13w
0x1800956a9  jz      short loc_180095705
0x1800956ab  lea     rdx, [rbp+var_48]; unsigned __int16 **
0x1800956af  mov     rcx, rbx; Src
0x1800956b2  call    ?SxCopyString@@YAJPEBGPEAPEAG@Z; SxCopyString(ushort const *,ushort * *)
0x1800956b7  mov     rsi, [rbp+var_48]
0x1800956bb  test    eax, eax
0x1800956bd  mov     [rbp+var_40], eax
0x1800956c0  mov     eax, 1CFh
0x1800956c5  js      short loc_180095737
0x1800956c7  mov     rdx, rsi
0x1800956ca  mov     [rbp+var_3C], ax
0x1800956ce  mov     rcx, rdi
0x1800956d1  call    ?Append@?$CSxSimpleArray@PEAG@@QEAAJPEAG@Z; CSxSimpleArray<ushort *>::Append(ushort *)
0x1800956d6  mov     [rbp+var_40], eax
0x1800956d9  test    eax, eax
0x1800956db  mov     eax, 1D0h
0x1800956e0  js      short loc_180095737
0x1800956e2  mov     [rbp+var_3C], ax
0x1800956e6  mov     rsi, r13
0x1800956e9  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800956ed  mov     [rbp+var_48], r13
0x1800956f1  inc     rax
0x1800956f4  cmp     [rbx+rax*2], r13w
0x1800956f9  jnz     short loc_1800956F1
0x1800956fb  lea     rbx, [rbx+rax*2]
0x1800956ff  add     rbx, 2
0x180095703  jmp     short loc_1800956A5
0x180095705  mov     eax, [rdi+10h]
0x180095708  mov     rcx, rdi; Block
0x18009570b  mov     [r14], eax
0x18009570e  mov     rax, [rdi+8]
0x180095712  mov     [rdi+8], r13
0x180095716  mov     [rdi+10h], r13
0x18009571a  mov     rdi, r13
0x18009571d  mov     [r15], rax
0x180095720  call    ?Release@?$CSxSimpleArray@PEAG@@QEAAKXZ; CSxSimpleArray<ushort *>::Release(void)
0x180095725  jmp     short loc_18009573B
0x180095727  mov     [rbp+var_40], 8007000Eh
0x18009572e  jmp     short loc_180095737
0x180095730  mov     [rbp+var_40], 80070057h
0x180095737  mov     [rbp+var_3A], ax
0x18009573b  mov     rcx, r12; pv
0x18009573e  call    cs:__imp_CoTaskMemFree
0x180095745  nop     dword ptr [rax+rax+00h]
0x18009574a  mov     rcx, rsi; pv
0x18009574d  call    cs:__imp_CoTaskMemFree
0x180095754  nop     dword ptr [rax+rax+00h]
0x180095759  test    rdi, rdi
0x18009575c  jz      short loc_18009578C
0x18009575e  mov     esi, r13d
0x180095761  cmp     [rdi+10h], r13d
0x180095765  jbe     short loc_18009578C
0x180095767  mov     rcx, [rdi+8]
0x18009576b  mov     ebx, esi
0x18009576d  mov     rcx, [rcx+rbx*8]; pv
0x180095771  call    cs:__imp_CoTaskMemFree
0x180095778  nop     dword ptr [rax+rax+00h]
0x18009577d  mov     rax, [rdi+8]
0x180095781  inc     esi
0x180095783  mov     [rax+rbx*8], r13
0x180095787  cmp     esi, [rdi+10h]
0x18009578a  jb      short loc_180095767
0x18009578c  mov     rcx, [rbp+pv]
0x180095790  test    rcx, rcx
0x180095793  jz      short loc_1800957D3
0x180095795  mov     esi, r13d
0x180095798  cmp     [rbp+arg_8], r13d
0x18009579c  jbe     short loc_1800957C3
0x18009579e  mov     ebx, esi
0x1800957a0  mov     rcx, [rcx+rbx*8]; pv
0x1800957a4  call    cs:__imp_CoTaskMemFree
0x1800957ab  nop     dword ptr [rax+rax+00h]
0x1800957b0  mov     rax, [rbp+pv]
0x1800957b4  inc     esi
0x1800957b6  mov     [rax+rbx*8], r13
0x1800957ba  mov     rcx, [rbp+pv]; pv
0x1800957be  cmp     esi, [rbp+arg_8]
0x1800957c1  jb      short loc_18009579E
0x1800957c3  call    cs:__imp_CoTaskMemFree
0x1800957ca  nop     dword ptr [rax+rax+00h]
0x1800957cf  mov     [rbp+pv], r13
0x1800957d3  mov     ebx, [rbp+var_40]
0x1800957d6  test    rdi, rdi
0x1800957d9  jz      short loc_1800957E3
0x1800957db  mov     rcx, rdi; Block
0x1800957de  call    ?Release@?$CSxSimpleArray@PEAG@@QEAAKXZ; CSxSimpleArray<ushort *>::Release(void)
0x1800957e3  lea     rcx, [rbp+var_40]; this
0x1800957e7  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x1800957ec  mov     eax, ebx
0x1800957ee  add     rsp, 78h
0x1800957f2  pop     r15
0x1800957f4  pop     r14
0x1800957f6  pop     r13
0x1800957f8  pop     r12
0x1800957fa  pop     rdi
0x1800957fb  pop     rsi
0x1800957fc  pop     rbx
0x1800957fd  pop     rbp
0x1800957fe  retn
```
