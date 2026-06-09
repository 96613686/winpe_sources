# XwParseWlanAPProfile(IXMLDOMNode *,_PM_PROFILE *,ulong *)

- ea: `0x1800470b8`
- end: `0x180047213`
- name: `?XwParseWlanAPProfile@@YAKPEAUIXMLDOMNode@@PEAU_PM_PROFILE@@PEAK@Z`
- size: `347`
- prototype: `unsigned int __fastcall(struct IXMLDOMNode *, struct _PM_PROFILE *, unsigned int *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180044264`

## callees

- `0x180009654`
- `0x18000dea8`
- `0x18000e3d0`
- `0x18000fe30`
- `0x180044d40`
- `0x1800470b8`
- `0x180047db4`
- `0x180048080`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047120`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800471e9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047120`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800471e9`

## string_xrefs

- `0x18004714b`: `WLANAPProfile:SSIDConfig`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall XwParseWlanAPProfile(struct IXMLDOMNode *a1, struct _PM_PROFILE *a2, unsigned int *a3)
{
  unsigned int NodeStringValue; // ebx
  _DWORD *v7; // rdi
  unsigned int FirstNode; // eax
  __int64 v9; // r9
  unsigned int v10; // eax
  void *v12; // rax
  int v13; // [rsp+20h] [rbp-38h]
  const unsigned __int16 *v14; // [rsp+28h] [rbp-30h]
  int *v15; // [rsp+30h] [rbp-28h]
  struct IXMLDOMNode *v16; // [rsp+68h] [rbp+10h] BYREF
  struct IXMLDOMNode *v17; // [rsp+70h] [rbp+18h] BYREF

  v17 = 0;
  v16 = 0;
  if ( a3 )
    *a3 = 0;
  NodeStringValue = XcGetNodeStringValue(a1, L"WLANAPProfile:name", (unsigned __int16 *)a2 + 12, 0x100u, v13, v14, v15);
  if ( !NodeStringValue )
  {
    v7 = Xc_Process_user_allocate(0x48u);
    if ( !v7 )
    {
      NodeStringValue = GetLastError();
      goto LABEL_12;
    }
    *v7 = 1;
    v7[5] = 8;
    v7[4] = 1;
    v7[1] |= 3u;
    v7[6] = 0;
    FirstNode = XcGetFirstNode(a1, L"WLANAPProfile:SSIDConfig", &v17);
    NodeStringValue = FirstNode;
    if ( FirstNode != 1168 )
    {
      if ( FirstNode )
        goto LABEL_11;
      NodeStringValue = XwpParseAPSSIDConfig(v17, (__int64)v7, a3, v9);
      if ( NodeStringValue )
        goto LABEL_11;
      v10 = XcGetFirstNode(a1, L"WLANAPProfile:MSM", &v16);
      NodeStringValue = v10;
      if ( v10 != 1168 )
      {
        if ( !v10 )
        {
          v12 = Xc_Process_user_allocate(0x1C8u);
          *((_QWORD *)v7 + 4) = v12;
          if ( v12 )
          {
            NodeStringValue = XwpParseAPMSMSettings(v16);
            if ( !NodeStringValue )
            {
              *((_QWORD *)a2 + 69) = v7;
              goto LABEL_12;
            }
          }
          else
          {
            NodeStringValue = GetLastError();
          }
        }
        goto LABEL_11;
      }
    }
    NodeStringValue = 1206;
LABEL_11:
    WcFreeDot11ACProfile(v7);
  }
LABEL_12:
  ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(&v16);
  ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(&v17);
  return NodeStringValue;
}

```

## disassembly

```asm
0x1800470b8  mov     rax, rsp
0x1800470bb  mov     [rax+8], rbx
0x1800470bf  mov     [rax+20h], rbp
0x1800470c3  push    rsi
0x1800470c4  push    rdi
0x1800470c5  push    r14
0x1800470c7  sub     rsp, 40h
0x1800470cb  mov     rsi, r8
0x1800470ce  mov     r14, rdx
0x1800470d1  mov     rbp, rcx
0x1800470d4  mov     qword ptr [rax+18h], 0
0x1800470dc  mov     qword ptr [rax+10h], 0
0x1800470e4  test    r8, r8
0x1800470e7  jz      short loc_1800470F0
0x1800470e9  mov     dword ptr [r8], 0
0x1800470f0  lea     r8, [rdx+18h]; unsigned __int16 *
0x1800470f4  mov     r9d, 100h; unsigned __int64
0x1800470fa  lea     rdx, aWlanapprofileN; "WLANAPProfile:name"
0x180047101  call    ?XcGetNodeStringValue@@YAKPEAUIXMLDOMNode@@PEBGPEAG_KH1PEAH@Z; XcGetNodeStringValue(IXMLDOMNode *,ushort const *,ushort *,unsigned __int64,int,ushort const *,int *)
0x180047106  mov     ebx, eax
0x180047108  test    eax, eax
0x18004710a  jnz     loc_1800471A8
0x180047110  lea     ecx, [rax+48h]; dwBytes
0x180047113  call    ?Xc_Process_user_allocate@@YAPEAX_K@Z; Xc_Process_user_allocate(unsigned __int64)
0x180047118  mov     rdi, rax
0x18004711b  test    rax, rax
0x18004711e  jnz     short loc_18004712A
0x180047120  call    cs:__imp_GetLastError
0x180047126  mov     ebx, eax
0x180047128  jmp     short loc_1800471A8
0x18004712a  mov     eax, 1
0x18004712f  mov     [rdi], eax
0x180047131  mov     dword ptr [rdi+14h], 8
0x180047138  mov     [rdi+10h], eax
0x18004713b  or      dword ptr [rdi+4], 3
0x18004713f  mov     dword ptr [rdi+18h], 0
0x180047146  lea     r8, [rsp+58h+arg_10]; struct IXMLDOMNode **
0x18004714b  lea     rdx, aWlanapprofileS; "WLANAPProfile:SSIDConfig"
0x180047152  mov     rcx, rbp; struct IXMLDOMNode *
0x180047155  call    ?XcGetFirstNode@@YAKPEAUIXMLDOMNode@@PEBGPEAPEAU1@@Z; XcGetFirstNode(IXMLDOMNode *,ushort const *,IXMLDOMNode * *)
0x18004715a  mov     ebx, eax
0x18004715c  cmp     eax, 490h
0x180047161  jz      short loc_18004719A
0x180047163  test    eax, eax
0x180047165  jnz     short loc_18004719F
0x180047167  mov     r8, rsi
0x18004716a  mov     rdx, rdi
0x18004716d  mov     rcx, [rsp+58h+arg_10]
0x180047172  call    XwpParseAPSSIDConfig
0x180047177  mov     ebx, eax
0x180047179  test    eax, eax
0x18004717b  jnz     short loc_18004719F
0x18004717d  lea     r8, [rsp+58h+arg_8]; struct IXMLDOMNode **
0x180047182  lea     rdx, aWlanapprofileM; "WLANAPProfile:MSM"
0x180047189  mov     rcx, rbp; struct IXMLDOMNode *
0x18004718c  call    ?XcGetFirstNode@@YAKPEAUIXMLDOMNode@@PEBGPEAPEAU1@@Z; XcGetFirstNode(IXMLDOMNode *,ushort const *,IXMLDOMNode * *)
0x180047191  mov     ebx, eax
0x180047193  cmp     eax, 490h
0x180047198  jnz     short loc_1800471D2
0x18004719a  mov     ebx, 4B6h
0x18004719f  mov     rcx, rdi; lpMem
0x1800471a2  call    WcFreeDot11ACProfile
0x1800471a7  nop
0x1800471a8  lea     rcx, [rsp+58h+arg_8]
0x1800471ad  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x1800471b2  nop
0x1800471b3  lea     rcx, [rsp+58h+arg_10]
0x1800471b8  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x1800471bd  mov     eax, ebx
0x1800471bf  mov     rbx, [rsp+58h+arg_0]
0x1800471c4  mov     rbp, [rsp+58h+arg_18]
0x1800471c9  add     rsp, 40h
0x1800471cd  pop     r14
0x1800471cf  pop     rdi
0x1800471d0  pop     rsi
0x1800471d1  retn
0x1800471d2  test    eax, eax
0x1800471d4  jnz     short loc_18004719F
0x1800471d6  mov     ecx, 1C8h; dwBytes
0x1800471db  call    ?Xc_Process_user_allocate@@YAPEAX_K@Z; Xc_Process_user_allocate(unsigned __int64)
0x1800471e0  mov     [rdi+20h], rax
0x1800471e4  test    rax, rax
0x1800471e7  jnz     short loc_1800471F3
0x1800471e9  call    cs:__imp_GetLastError
0x1800471ef  mov     ebx, eax
0x1800471f1  jmp     short loc_18004719F
0x1800471f3  mov     r8, rsi
0x1800471f6  mov     rdx, rax
0x1800471f9  mov     rcx, [rsp+58h+arg_8]; struct IXMLDOMNode *
0x1800471fe  call    XwpParseAPMSMSettings
0x180047203  mov     ebx, eax
0x180047205  test    eax, eax
0x180047207  jnz     short loc_18004719F
0x180047209  mov     [r14+228h], rdi
0x180047210  jmp     short loc_1800471A8
```
