# CUPnPEventingManager::AddSubscriber(ulong,ushort const * *,ushort const *,ushort const *,ulong *,ushort * *)

- ea: `0x180034030`
- end: `0x18003436e`
- name: `?AddSubscriber@CUPnPEventingManager@@UEAAJKPEAPEBGPEBG1PEAKPEAPEAG@Z`
- size: `830`
- prototype: `__int64 __fastcall(CUPnPEventingManager *this, unsigned int, const unsigned __int16 **, const unsigned __int16 *, unsigned __int16 *, unsigned int *, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000db4c`
- `0x180013180`
- `0x18001ebf8`
- `0x1800300e4`
- `0x180034030`
- `0x180034374`
- `0x180045ce0`
- `0x180050790`
- `0x180055010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18003425e`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180034267`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18003425e`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180034267`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800341e1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800341e1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180034207`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180034285`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180034293`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800342b5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800342bf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800342c9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800342d3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180034207`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180034285`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180034293`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800342b5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800342bf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800342c9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800342d3`

## string_xrefs

- `0x18003422c`: `CUPnPEventingManager::AddSubscriber - CoTaskMemAlloc()`

## pseudocode

```c
__int64 __fastcall CUPnPEventingManager::AddSubscriber(
        CUPnPEventingManager *this,
        unsigned int a2,
        const unsigned __int16 **a3,
        const unsigned __int16 *a4,
        unsigned __int16 *a5,
        unsigned int *a6,
        unsigned __int16 **a7)
{
  __int64 result; // rax
  unsigned int v11; // ecx
  int v12; // edi
  struct IUPnPAutomationProxy *v13; // rcx
  const unsigned __int16 *v14; // rcx
  wchar_t *v15; // r13
  __int64 v16; // rax
  SIZE_T v17; // r14
  unsigned __int16 *v18; // rax
  unsigned int i; // esi
  unsigned int v20; // [rsp+40h] [rbp-41h] BYREF
  unsigned int v21; // [rsp+44h] [rbp-3Dh] BYREF
  void *Block; // [rsp+48h] [rbp-39h] BYREF
  LPVOID pv; // [rsp+50h] [rbp-31h] BYREF
  unsigned __int16 **v24; // [rsp+58h] [rbp-29h] BYREF
  struct tagVARIANT *v25; // [rsp+60h] [rbp-21h] BYREF
  LPVOID v26; // [rsp+68h] [rbp-19h] BYREF
  STRSAFE_PCNZWCH pszSrc[10]; // [rsp+70h] [rbp-11h] BYREF

  pszSrc[0] = 0;
  v20 = 0;
  v24 = 0;
  pv = 0;
  v25 = 0;
  v21 = 0;
  v26 = 0;
  result = HrIsAllowedCOMCallLocality(1);
  if ( (int)result >= 0 )
  {
    if ( *((_DWORD *)this + 24) == 2 && *((_QWORD *)this + 9) && *((_QWORD *)this + 11) )
    {
      if ( a3 && a2 && a6 && a7 )
      {
        v11 = 0;
        do
        {
          if ( !a3[v11] )
            return 2147942487LL;
          ++v11;
        }
        while ( v11 < a2 );
        *a7 = 0;
        v12 = (*(__int64 (__fastcall **)(_QWORD, unsigned int *, LPVOID *))(**((_QWORD **)this + 11) + 32LL))(
                *((_QWORD *)this + 11),
                &v21,
                &v26);
        if ( v12 < 0 )
        {
LABEL_33:
          if ( v12 && WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
            WPP_SF_sd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              14,
              (unsigned int)WPP_26899187c1a539900c7f96418485818e_Traceguids,
              (unsigned int)"CUPnPEventingManager::AddSubscriber",
              v12);
          return (unsigned int)v12;
        }
        v12 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, LPVOID, unsigned int *, unsigned __int16 ***, struct tagVARIANT **, LPVOID *))(**((_QWORD **)this + 11) + 40LL))(
                *((_QWORD *)this + 11),
                v21,
                v26,
                &v20,
                &v24,
                &v25,
                &pv);
        if ( v12 < 0 )
        {
LABEL_32:
          CoTaskMemFree(v26);
          goto LABEL_33;
        }
        v12 = HrComposeEventBody(v13, v20, v24, (unsigned __int16 **)pv, v25, (BSTR)pszSrc);
        if ( v12 < 0 )
        {
LABEL_29:
          for ( i = 0; i < v20; ++i )
          {
            CoTaskMemFree(*((LPVOID *)pv + i));
            CoTaskMemFree(v24[i]);
            SafeClearVariant(&v25[i]);
          }
          CoTaskMemFree(pv);
          CoTaskMemFree(v24);
          CoTaskMemFree(v25);
          goto LABEL_32;
        }
        v14 = (const unsigned __int16 *)*((_QWORD *)this + 9);
        Block = 0;
        v15 = (wchar_t *)pszSrc[0];
        v12 = HrAddSubscriber(v14, a4, a5, a2, a3, pszSrc[0], a6, (unsigned __int16 **)&Block);
        if ( v12 < 0 )
        {
LABEL_28:
          free(v15);
          goto LABEL_29;
        }
        v16 = -1;
        do
          ++v16;
        while ( *((_WORD *)Block + v16) );
        v17 = (unsigned int)(2 * v16 + 2);
        v18 = (unsigned __int16 *)CoTaskMemAlloc(v17);
        *a7 = v18;
        if ( v18 )
        {
          v12 = StringCbCopyW(v18, (unsigned int)v17, (const unsigned __int16 *)Block);
          if ( v12 >= 0 )
          {
LABEL_27:
            free(Block);
            goto LABEL_28;
          }
          CoTaskMemFree(*a7);
          *a7 = 0;
        }
        else
        {
          if ( v12 && WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
            WPP_SF_sd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              13,
              (unsigned int)WPP_26899187c1a539900c7f96418485818e_Traceguids,
              (unsigned int)"CUPnPEventingManager::AddSubscriber - CoTaskMemAlloc()",
              v12);
          v12 = -2147024882;
        }
        HrRemoveSubscriber(*((const unsigned __int16 **)this + 9), (const unsigned __int16 *)Block);
        goto LABEL_27;
      }
      return 2147942487LL;
    }
    else
    {
      if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        WPP_SF_sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          12,
          (unsigned int)WPP_26899187c1a539900c7f96418485818e_Traceguids,
          (unsigned int)"AddSubscriber failed, CUPnPEventingManager is not initialized!",
          255);
      return 2147549183LL;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180034030  mov     [rsp-8+Src], r9
0x180034035  push    rbp
0x180034036  push    rbx
0x180034037  push    rsi
0x180034038  push    rdi
0x180034039  push    r12
0x18003403b  push    r13
0x18003403d  push    r14
0x18003403f  push    r15
0x180034041  lea     rbp, [rsp-7]
0x180034046  sub     rsp, 88h
0x18003404d  xor     edi, edi
0x18003404f  mov     rbx, rcx
0x180034052  mov     r12, r8
0x180034055  mov     [rbp+3Fh+var_50], rdi
0x180034059  mov     r14d, edx
0x18003405c  mov     [rbp+3Fh+var_80], edi
0x18003405f  mov     [rbp+3Fh+var_68], rdi
0x180034063  lea     ecx, [rdi+1]
0x180034066  mov     [rbp+3Fh+pv], rdi
0x18003406a  mov     [rbp+3Fh+var_60], rdi
0x18003406e  mov     [rbp+3Fh+var_7C], edi
0x180034071  mov     [rbp+3Fh+var_58], rdi
0x180034075  call    ?HrIsAllowedCOMCallLocality@@YAJW4CALL_LOCALITY@@@Z; HrIsAllowedCOMCallLocality(CALL_LOCALITY)
0x18003407a  test    eax, eax
0x18003407c  js      loc_18003435A
0x180034082  mov     eax, [rbx+60h]
0x180034085  cmp     eax, 2
0x180034088  jnz     loc_18003431A
0x18003408e  cmp     [rbx+48h], rdi
0x180034092  jz      loc_18003431A
0x180034098  cmp     [rbx+58h], rdi
0x18003409c  jz      loc_18003431A
0x1800340a2  test    r12, r12
0x1800340a5  jz      loc_180034313
0x1800340ab  test    r14d, r14d
0x1800340ae  jz      loc_180034313
0x1800340b4  mov     r13, [rbp+3Fh+arg_28]
0x1800340b8  test    r13, r13
0x1800340bb  jz      loc_180034313
0x1800340c1  mov     rsi, [rbp+3Fh+arg_30]
0x1800340c5  test    rsi, rsi
0x1800340c8  jz      loc_180034313
0x1800340ce  mov     ecx, edi
0x1800340d0  test    r14d, r14d
0x1800340d3  jz      short loc_1800340E8
0x1800340d5  mov     eax, ecx
0x1800340d7  cmp     [r12+rax*8], rdi
0x1800340db  jz      loc_180034313
0x1800340e1  inc     ecx
0x1800340e3  cmp     ecx, r14d
0x1800340e6  jb      short loc_1800340D5
0x1800340e8  mov     [rsi], rdi
0x1800340eb  lea     r8, [rbp+3Fh+var_58]
0x1800340ef  mov     rcx, [rbx+58h]
0x1800340f3  lea     rdx, [rbp+3Fh+var_7C]
0x1800340f7  mov     rax, [rcx]
0x1800340fa  mov     rax, [rax+20h]
0x1800340fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034103  lea     r15, WPP_GLOBAL_Control
0x18003410a  mov     edi, eax
0x18003410c  test    eax, eax
0x18003410e  js      loc_1800342D9
0x180034114  mov     rcx, [rbx+58h]
0x180034118  lea     rdx, [rbp+3Fh+pv]
0x18003411c  mov     r8, [rbp+3Fh+var_58]
0x180034120  lea     r9, [rbp+3Fh+var_80]
0x180034124  mov     [rsp+0C0h+var_90], rdx
0x180034129  lea     rdx, [rbp+3Fh+var_60]
0x18003412d  mov     [rsp+0C0h+pszSrc], rdx
0x180034132  lea     rdx, [rbp+3Fh+var_68]
0x180034136  mov     rax, [rcx]
0x180034139  mov     [rsp+0C0h+var_A0], rdx
0x18003413e  mov     edx, [rbp+3Fh+var_7C]
0x180034141  mov     rax, [rax+28h]
0x180034145  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003414a  mov     edi, eax
0x18003414c  test    eax, eax
0x18003414e  js      loc_1800342CF
0x180034154  mov     r9, [rbp+3Fh+pv]; unsigned __int16 **
0x180034158  lea     rax, [rbp+3Fh+var_50]
0x18003415c  mov     r8, [rbp+3Fh+var_68]; unsigned __int16 **
0x180034160  mov     edx, [rbp+3Fh+var_80]; unsigned int
0x180034163  mov     [rsp+0C0h+pszSrc], rax; pbstr
0x180034168  mov     rax, [rbp+3Fh+var_60]
0x18003416c  mov     [rsp+0C0h+var_A0], rax; struct tagVARIANT *
0x180034171  call    ?HrComposeEventBody@@YAJPEAUIUPnPAutomationProxy@@KPEAPEAG1PEAUtagVARIANT@@1@Z; HrComposeEventBody(IUPnPAutomationProxy *,ulong,ushort * *,ushort * *,tagVARIANT *,ushort * *)
0x180034176  mov     edi, eax
0x180034178  xor     eax, eax
0x18003417a  test    edi, edi
0x18003417c  js      loc_18003426F
0x180034182  mov     r8, [rbp+3Fh+arg_20]; unsigned __int16 *
0x180034186  mov     r9d, r14d; unsigned int
0x180034189  mov     rdx, [rbp+3Fh+Src]; Src
0x18003418d  mov     rcx, [rbx+48h]; unsigned __int16 *
0x180034191  mov     [rbp+3Fh+Block], rax
0x180034195  lea     rax, [rbp+3Fh+Block]
0x180034199  mov     [rsp+0C0h+var_88], rax; unsigned __int16 **
0x18003419e  mov     [rsp+0C0h+var_90], r13; unsigned int *
0x1800341a3  mov     r13, [rbp+3Fh+var_50]
0x1800341a7  mov     [rsp+0C0h+pszSrc], r13; pszSrc
0x1800341ac  mov     [rsp+0C0h+var_A0], r12; unsigned __int16 **
0x1800341b1  call    ?HrAddSubscriber@@YAJPEBG00KPEAPEBG0PEAKPEAPEAG@Z; HrAddSubscriber(ushort const *,ushort const *,ushort const *,ulong,ushort const * *,ushort const *,ulong *,ushort * *)
0x1800341b6  xor     r12d, r12d
0x1800341b9  mov     edi, eax
0x1800341bb  test    eax, eax
0x1800341bd  js      loc_180034264
0x1800341c3  mov     rcx, [rbp+3Fh+Block]
0x1800341c7  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800341cb  inc     rax
0x1800341ce  cmp     [rcx+rax*2], r12w
0x1800341d3  jnz     short loc_1800341CB
0x1800341d5  lea     eax, ds:2[rax*2]
0x1800341dc  mov     ecx, eax; cb
0x1800341de  mov     r14d, eax
0x1800341e1  call    cs:__imp_CoTaskMemAlloc
0x1800341e7  mov     [rsi], rax
0x1800341ea  test    rax, rax
0x1800341ed  jz      short loc_180034212
0x1800341ef  mov     r8, [rbp+3Fh+Block]; unsigned __int16 *
0x1800341f3  mov     edx, r14d; unsigned __int64
0x1800341f6  mov     rcx, rax; unsigned __int16 *
0x1800341f9  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x1800341fe  mov     edi, eax
0x180034200  test    eax, eax
0x180034202  jns     short loc_18003425A
0x180034204  mov     rcx, [rsi]; pv
0x180034207  call    cs:__imp_CoTaskMemFree
0x18003420d  mov     [rsi], r12
0x180034210  jmp     short loc_18003424D
0x180034212  test    edi, edi
0x180034214  jz      short loc_180034248
0x180034216  mov     rcx, cs:WPP_GLOBAL_Control
0x18003421d  cmp     rcx, r15
0x180034220  jz      short loc_180034248
0x180034222  test    byte ptr [rcx+1Ch], 1
0x180034226  jz      short loc_180034248
0x180034228  mov     rcx, [rcx+10h]
0x18003422c  lea     r9, aCupnpeventingm_1; "CUPnPEventingManager::AddSubscriber - C"...
0x180034233  mov     edx, 0Dh
0x180034238  mov     dword ptr [rsp+0C0h+var_A0], edi
0x18003423c  lea     r8, WPP_26899187c1a539900c7f96418485818e_Traceguids
0x180034243  call    WPP_SF_sd
0x180034248  mov     edi, 8007000Eh
0x18003424d  mov     rdx, [rbp+3Fh+Block]; unsigned __int16 *
0x180034251  mov     rcx, [rbx+48h]; unsigned __int16 *
0x180034255  call    ?HrRemoveSubscriber@@YAJPEBG0@Z; HrRemoveSubscriber(ushort const *,ushort const *)
0x18003425a  mov     rcx, [rbp+3Fh+Block]; Block
0x18003425e  call    cs:__imp_free
0x180034264  mov     rcx, r13; Block
0x180034267  call    cs:__imp_free
0x18003426d  jmp     short loc_180034272
0x18003426f  xor     r12d, r12d
0x180034272  mov     esi, r12d
0x180034275  cmp     [rbp+3Fh+var_80], r12d
0x180034279  jbe     short loc_1800342B1
0x18003427b  mov     rcx, [rbp+3Fh+pv]
0x18003427f  mov     ebx, esi
0x180034281  mov     rcx, [rcx+rbx*8]; pv
0x180034285  call    cs:__imp_CoTaskMemFree
0x18003428b  mov     rcx, [rbp+3Fh+var_68]
0x18003428f  mov     rcx, [rcx+rbx*8]; pv
0x180034293  call    cs:__imp_CoTaskMemFree
0x180034299  mov     rax, [rbp+3Fh+var_60]
0x18003429d  lea     rcx, [rbx+rbx*2]
0x1800342a1  lea     rcx, [rax+rcx*8]; VARIANT *
0x1800342a5  call    ?SafeClearVariant@@YAXPEAUtagVARIANT@@@Z; SafeClearVariant(tagVARIANT *)
0x1800342aa  inc     esi
0x1800342ac  cmp     esi, [rbp+3Fh+var_80]
0x1800342af  jb      short loc_18003427B
0x1800342b1  mov     rcx, [rbp+3Fh+pv]; pv
0x1800342b5  call    cs:__imp_CoTaskMemFree
0x1800342bb  mov     rcx, [rbp+3Fh+var_68]; pv
0x1800342bf  call    cs:__imp_CoTaskMemFree
0x1800342c5  mov     rcx, [rbp+3Fh+var_60]; pv
0x1800342c9  call    cs:__imp_CoTaskMemFree
0x1800342cf  mov     rcx, [rbp+3Fh+var_58]; pv
0x1800342d3  call    cs:__imp_CoTaskMemFree
0x1800342d9  test    edi, edi
0x1800342db  jz      short loc_18003430F
0x1800342dd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800342e4  cmp     rcx, r15
0x1800342e7  jz      short loc_18003430F
0x1800342e9  test    byte ptr [rcx+1Ch], 1
0x1800342ed  jz      short loc_18003430F
0x1800342ef  mov     rcx, [rcx+10h]
0x1800342f3  lea     r9, aCupnpeventingm_0; "CUPnPEventingManager::AddSubscriber"
0x1800342fa  mov     edx, 0Eh
0x1800342ff  mov     dword ptr [rsp+0C0h+var_A0], edi
0x180034303  lea     r8, WPP_26899187c1a539900c7f96418485818e_Traceguids
0x18003430a  call    WPP_SF_sd
0x18003430f  mov     eax, edi
0x180034311  jmp     short loc_18003435A
0x180034313  mov     eax, 80070057h
0x180034318  jmp     short loc_18003435A
0x18003431a  mov     rcx, cs:WPP_GLOBAL_Control
0x180034321  lea     r15, WPP_GLOBAL_Control
0x180034328  mov     ebx, 8000FFFFh
0x18003432d  cmp     rcx, r15
0x180034330  jz      short loc_180034358
0x180034332  test    byte ptr [rcx+1Ch], 1
0x180034336  jz      short loc_180034358
0x180034338  mov     rcx, [rcx+10h]
0x18003433c  lea     r9, aAddsubscriberF; "AddSubscriber failed, CUPnPEventingMana"...
0x180034343  mov     edx, 0Ch
0x180034348  mov     dword ptr [rsp+0C0h+var_A0], ebx
0x18003434c  lea     r8, WPP_26899187c1a539900c7f96418485818e_Traceguids
0x180034353  call    WPP_SF_sd
0x180034358  mov     eax, ebx
0x18003435a  add     rsp, 88h
0x180034361  pop     r15
0x180034363  pop     r14
0x180034365  pop     r13
0x180034367  pop     r12
0x180034369  pop     rdi
0x18003436a  pop     rsi
0x18003436b  pop     rbx
0x18003436c  pop     rbp
0x18003436d  retn
```
