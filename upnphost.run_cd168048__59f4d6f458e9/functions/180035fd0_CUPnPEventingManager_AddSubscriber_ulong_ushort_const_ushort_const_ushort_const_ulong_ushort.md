# CUPnPEventingManager::AddSubscriber(ulong,ushort const * *,ushort const *,ushort const *,ulong *,ushort * *)

- ea: `0x180035fd0`
- end: `0x18003634b`
- name: `?AddSubscriber@CUPnPEventingManager@@UEAAJKPEAPEBGPEBG1PEAKPEAPEAG@Z`
- size: `891`
- prototype: `__int64 __fastcall(CUPnPEventingManager *this, unsigned int, const unsigned __int16 **, const unsigned __int16 *, unsigned __int16 *, unsigned int *, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800071c0`
- `0x180013cd0`
- `0x1800200f4`
- `0x180031718`
- `0x180035fd0`
- `0x180036354`
- `0x180048984`
- `0x180053e18`
- `0x180059010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18003620a`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180036219`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18003620a`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180036219`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180036181`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180036181`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800361ad`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003623d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180036251`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180036279`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180036289`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180036299`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800362a9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800361ad`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003623d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180036251`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180036279`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180036289`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180036299`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800362a9`

## string_xrefs

- `0x1800361d8`: `CUPnPEventingManager::AddSubscriber - CoTaskMemAlloc()`

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
        v12 = HrAddSubscriber(v14, a4, (struct addrinfoW *)a5, a2, a3, pszSrc[0], a6, (unsigned __int16 **)&Block);
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
0x180035fd0  mov     [rsp-8+Src], r9
0x180035fd5  push    rbp
0x180035fd6  push    rbx
0x180035fd7  push    rsi
0x180035fd8  push    rdi
0x180035fd9  push    r12
0x180035fdb  push    r13
0x180035fdd  push    r14
0x180035fdf  push    r15
0x180035fe1  lea     rbp, [rsp-7]
0x180035fe6  sub     rsp, 88h
0x180035fed  xor     edi, edi
0x180035fef  mov     rbx, rcx
0x180035ff2  mov     r12, r8
0x180035ff5  mov     [rbp+3Fh+var_50], rdi
0x180035ff9  mov     r14d, edx
0x180035ffc  mov     [rbp+3Fh+var_80], edi
0x180035fff  mov     [rbp+3Fh+var_68], rdi
0x180036003  lea     ecx, [rdi+1]
0x180036006  mov     [rbp+3Fh+pv], rdi
0x18003600a  mov     [rbp+3Fh+var_60], rdi
0x18003600e  mov     [rbp+3Fh+var_7C], edi
0x180036011  mov     [rbp+3Fh+var_58], rdi
0x180036015  call    ?HrIsAllowedCOMCallLocality@@YAJW4CALL_LOCALITY@@@Z; HrIsAllowedCOMCallLocality(CALL_LOCALITY)
0x18003601a  test    eax, eax
0x18003601c  js      loc_180036336
0x180036022  mov     eax, [rbx+60h]
0x180036025  cmp     eax, 2
0x180036028  jnz     loc_1800362F6
0x18003602e  cmp     [rbx+48h], rdi
0x180036032  jz      loc_1800362F6
0x180036038  cmp     [rbx+58h], rdi
0x18003603c  jz      loc_1800362F6
0x180036042  test    r12, r12
0x180036045  jz      loc_1800362EF
0x18003604b  test    r14d, r14d
0x18003604e  jz      loc_1800362EF
0x180036054  mov     r13, [rbp+3Fh+arg_28]
0x180036058  test    r13, r13
0x18003605b  jz      loc_1800362EF
0x180036061  mov     rsi, [rbp+3Fh+arg_30]
0x180036065  test    rsi, rsi
0x180036068  jz      loc_1800362EF
0x18003606e  mov     ecx, edi
0x180036070  test    r14d, r14d
0x180036073  jz      short loc_180036088
0x180036075  mov     eax, ecx
0x180036077  cmp     [r12+rax*8], rdi
0x18003607b  jz      loc_1800362EF
0x180036081  inc     ecx
0x180036083  cmp     ecx, r14d
0x180036086  jb      short loc_180036075
0x180036088  mov     [rsi], rdi
0x18003608b  lea     r8, [rbp+3Fh+var_58]
0x18003608f  mov     rcx, [rbx+58h]
0x180036093  lea     rdx, [rbp+3Fh+var_7C]
0x180036097  mov     rax, [rcx]
0x18003609a  mov     rax, [rax+20h]
0x18003609e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800360a3  lea     r15, WPP_GLOBAL_Control
0x1800360aa  mov     edi, eax
0x1800360ac  test    eax, eax
0x1800360ae  js      loc_1800362B5
0x1800360b4  mov     rcx, [rbx+58h]
0x1800360b8  lea     rdx, [rbp+3Fh+pv]
0x1800360bc  mov     r8, [rbp+3Fh+var_58]
0x1800360c0  lea     r9, [rbp+3Fh+var_80]
0x1800360c4  mov     [rsp+0C0h+var_90], rdx
0x1800360c9  lea     rdx, [rbp+3Fh+var_60]
0x1800360cd  mov     [rsp+0C0h+pszSrc], rdx
0x1800360d2  lea     rdx, [rbp+3Fh+var_68]
0x1800360d6  mov     rax, [rcx]
0x1800360d9  mov     [rsp+0C0h+var_A0], rdx
0x1800360de  mov     edx, [rbp+3Fh+var_7C]
0x1800360e1  mov     rax, [rax+28h]
0x1800360e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800360ea  mov     edi, eax
0x1800360ec  test    eax, eax
0x1800360ee  js      loc_1800362A5
0x1800360f4  mov     r9, [rbp+3Fh+pv]; unsigned __int16 **
0x1800360f8  lea     rax, [rbp+3Fh+var_50]
0x1800360fc  mov     r8, [rbp+3Fh+var_68]; unsigned __int16 **
0x180036100  mov     edx, [rbp+3Fh+var_80]; unsigned int
0x180036103  mov     [rsp+0C0h+pszSrc], rax; pbstr
0x180036108  mov     rax, [rbp+3Fh+var_60]
0x18003610c  mov     [rsp+0C0h+var_A0], rax; struct tagVARIANT *
0x180036111  call    ?HrComposeEventBody@@YAJPEAUIUPnPAutomationProxy@@KPEAPEAG1PEAUtagVARIANT@@1@Z; HrComposeEventBody(IUPnPAutomationProxy *,ulong,ushort * *,ushort * *,tagVARIANT *,ushort * *)
0x180036116  mov     edi, eax
0x180036118  xor     eax, eax
0x18003611a  test    edi, edi
0x18003611c  js      loc_180036227
0x180036122  mov     r8, [rbp+3Fh+arg_20]; unsigned __int16 *
0x180036126  mov     r9d, r14d; unsigned int
0x180036129  mov     rdx, [rbp+3Fh+Src]; Src
0x18003612d  mov     rcx, [rbx+48h]; unsigned __int16 *
0x180036131  mov     [rbp+3Fh+Block], rax
0x180036135  lea     rax, [rbp+3Fh+Block]
0x180036139  mov     [rsp+0C0h+var_88], rax; unsigned __int16 **
0x18003613e  mov     [rsp+0C0h+var_90], r13; unsigned int *
0x180036143  mov     r13, [rbp+3Fh+var_50]
0x180036147  mov     [rsp+0C0h+pszSrc], r13; pszSrc
0x18003614c  mov     [rsp+0C0h+var_A0], r12; unsigned __int16 **
0x180036151  call    ?HrAddSubscriber@@YAJPEBG00KPEAPEBG0PEAKPEAPEAG@Z; HrAddSubscriber(ushort const *,ushort const *,ushort const *,ulong,ushort const * *,ushort const *,ulong *,ushort * *)
0x180036156  xor     r12d, r12d
0x180036159  mov     edi, eax
0x18003615b  test    eax, eax
0x18003615d  js      loc_180036216
0x180036163  mov     rcx, [rbp+3Fh+Block]
0x180036167  or      rax, 0FFFFFFFFFFFFFFFFh
0x18003616b  inc     rax
0x18003616e  cmp     [rcx+rax*2], r12w
0x180036173  jnz     short loc_18003616B
0x180036175  lea     eax, ds:2[rax*2]
0x18003617c  mov     ecx, eax; cb
0x18003617e  mov     r14d, eax
0x180036181  call    cs:__imp_CoTaskMemAlloc
0x180036188  nop     dword ptr [rax+rax+00h]
0x18003618d  mov     [rsi], rax
0x180036190  test    rax, rax
0x180036193  jz      short loc_1800361BE
0x180036195  mov     r8, [rbp+3Fh+Block]; unsigned __int16 *
0x180036199  mov     edx, r14d; unsigned __int64
0x18003619c  mov     rcx, rax; unsigned __int16 *
0x18003619f  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x1800361a4  mov     edi, eax
0x1800361a6  test    eax, eax
0x1800361a8  jns     short loc_180036206
0x1800361aa  mov     rcx, [rsi]; pv
0x1800361ad  call    cs:__imp_CoTaskMemFree
0x1800361b4  nop     dword ptr [rax+rax+00h]
0x1800361b9  mov     [rsi], r12
0x1800361bc  jmp     short loc_1800361F9
0x1800361be  test    edi, edi
0x1800361c0  jz      short loc_1800361F4
0x1800361c2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800361c9  cmp     rcx, r15
0x1800361cc  jz      short loc_1800361F4
0x1800361ce  test    byte ptr [rcx+1Ch], 1
0x1800361d2  jz      short loc_1800361F4
0x1800361d4  mov     rcx, [rcx+10h]
0x1800361d8  lea     r9, aCupnpeventingm_1; "CUPnPEventingManager::AddSubscriber - C"...
0x1800361df  mov     edx, 0Dh
0x1800361e4  mov     dword ptr [rsp+0C0h+var_A0], edi
0x1800361e8  lea     r8, WPP_26899187c1a539900c7f96418485818e_Traceguids
0x1800361ef  call    WPP_SF_sd
0x1800361f4  mov     edi, 8007000Eh
0x1800361f9  mov     rdx, [rbp+3Fh+Block]; unsigned __int16 *
0x1800361fd  mov     rcx, [rbx+48h]; unsigned __int16 *
0x180036201  call    ?HrRemoveSubscriber@@YAJPEBG0@Z; HrRemoveSubscriber(ushort const *,ushort const *)
0x180036206  mov     rcx, [rbp+3Fh+Block]; Block
0x18003620a  call    cs:__imp_free
0x180036211  nop     dword ptr [rax+rax+00h]
0x180036216  mov     rcx, r13; Block
0x180036219  call    cs:__imp_free
0x180036220  nop     dword ptr [rax+rax+00h]
0x180036225  jmp     short loc_18003622A
0x180036227  xor     r12d, r12d
0x18003622a  mov     esi, r12d
0x18003622d  cmp     [rbp+3Fh+var_80], r12d
0x180036231  jbe     short loc_180036275
0x180036233  mov     rcx, [rbp+3Fh+pv]
0x180036237  mov     ebx, esi
0x180036239  mov     rcx, [rcx+rbx*8]; pv
0x18003623d  call    cs:__imp_CoTaskMemFree
0x180036244  nop     dword ptr [rax+rax+00h]
0x180036249  mov     rcx, [rbp+3Fh+var_68]
0x18003624d  mov     rcx, [rcx+rbx*8]; pv
0x180036251  call    cs:__imp_CoTaskMemFree
0x180036258  nop     dword ptr [rax+rax+00h]
0x18003625d  mov     rax, [rbp+3Fh+var_60]
0x180036261  lea     rcx, [rbx+rbx*2]
0x180036265  lea     rcx, [rax+rcx*8]; VARIANT *
0x180036269  call    ?SafeClearVariant@@YAXPEAUtagVARIANT@@@Z; SafeClearVariant(tagVARIANT *)
0x18003626e  inc     esi
0x180036270  cmp     esi, [rbp+3Fh+var_80]
0x180036273  jb      short loc_180036233
0x180036275  mov     rcx, [rbp+3Fh+pv]; pv
0x180036279  call    cs:__imp_CoTaskMemFree
0x180036280  nop     dword ptr [rax+rax+00h]
0x180036285  mov     rcx, [rbp+3Fh+var_68]; pv
0x180036289  call    cs:__imp_CoTaskMemFree
0x180036290  nop     dword ptr [rax+rax+00h]
0x180036295  mov     rcx, [rbp+3Fh+var_60]; pv
0x180036299  call    cs:__imp_CoTaskMemFree
0x1800362a0  nop     dword ptr [rax+rax+00h]
0x1800362a5  mov     rcx, [rbp+3Fh+var_58]; pv
0x1800362a9  call    cs:__imp_CoTaskMemFree
0x1800362b0  nop     dword ptr [rax+rax+00h]
0x1800362b5  test    edi, edi
0x1800362b7  jz      short loc_1800362EB
0x1800362b9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800362c0  cmp     rcx, r15
0x1800362c3  jz      short loc_1800362EB
0x1800362c5  test    byte ptr [rcx+1Ch], 1
0x1800362c9  jz      short loc_1800362EB
0x1800362cb  mov     rcx, [rcx+10h]
0x1800362cf  lea     r9, aCupnpeventingm_0; "CUPnPEventingManager::AddSubscriber"
0x1800362d6  mov     edx, 0Eh
0x1800362db  mov     dword ptr [rsp+0C0h+var_A0], edi
0x1800362df  lea     r8, WPP_26899187c1a539900c7f96418485818e_Traceguids
0x1800362e6  call    WPP_SF_sd
0x1800362eb  mov     eax, edi
0x1800362ed  jmp     short loc_180036336
0x1800362ef  mov     eax, 80070057h
0x1800362f4  jmp     short loc_180036336
0x1800362f6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800362fd  lea     r15, WPP_GLOBAL_Control
0x180036304  mov     ebx, 8000FFFFh
0x180036309  cmp     rcx, r15
0x18003630c  jz      short loc_180036334
0x18003630e  test    byte ptr [rcx+1Ch], 1
0x180036312  jz      short loc_180036334
0x180036314  mov     rcx, [rcx+10h]
0x180036318  lea     r9, aAddsubscriberF; "AddSubscriber failed, CUPnPEventingMana"...
0x18003631f  mov     edx, 0Ch
0x180036324  mov     dword ptr [rsp+0C0h+var_A0], ebx
0x180036328  lea     r8, WPP_26899187c1a539900c7f96418485818e_Traceguids
0x18003632f  call    WPP_SF_sd
0x180036334  mov     eax, ebx
0x180036336  add     rsp, 88h
0x18003633d  pop     r15
0x18003633f  pop     r14
0x180036341  pop     r13
0x180036343  pop     r12
0x180036345  pop     rdi
0x180036346  pop     rsi
0x180036347  pop     rbx
0x180036348  pop     rbp
0x180036349  retn
```
