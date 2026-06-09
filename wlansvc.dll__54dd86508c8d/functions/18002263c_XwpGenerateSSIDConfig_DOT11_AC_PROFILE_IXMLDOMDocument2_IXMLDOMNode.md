# XwpGenerateSSIDConfig(_DOT11_AC_PROFILE *,IXMLDOMDocument2 *,IXMLDOMNode *)

- ea: `0x18002263c`
- end: `0x180022beb`
- name: `?XwpGenerateSSIDConfig@@YAKPEAU_DOT11_AC_PROFILE@@PEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@@Z`
- size: `1455`
- prototype: `unsigned int(struct _DOT11_AC_PROFILE *, struct IXMLDOMDocument2 *, struct IXMLDOMNode *)`
- caller_count: `2`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800258d8`
- `0x1801b3814`

## callees

- `0x1800220d8`
- `0x18002263c`
- `0x180024930`
- `0x180026e60`
- `0x180040f20`
- `0x1800656f0`
- `0x18006fd60`
- `0x180084dc8`
- `0x180106340`
- `0x18022c010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180022838`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180022838`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002275d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002282a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002275d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002282a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002276e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002276e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002277f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800229c9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002277f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800229c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800229b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800229c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800229b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800229c1`

## string_xrefs

- `0x18002268f`: `http://www.microsoft.com/networking/WLAN/profile/v1`
- `0x180022726`: `http://www.microsoft.com/networking/WLAN/profile/v1`
- `0x18002280f`: `http://www.microsoft.com/networking/WLAN/profile/v1`
- `0x18002294a`: `http://www.microsoft.com/networking/WLAN/profile/v1`
- `0x180022976`: `http://www.microsoft.com/networking/WLAN/profile/v1`
- `0x180022696`: `SSIDConfig`
- `0x180022a96`: `http://www.microsoft.com/networking/WLAN/profile/v2`
- `0x180022af9`: `http://www.microsoft.com/networking/WLAN/profile/v2`
- `0x180022b2d`: `http://www.microsoft.com/networking/WLAN/profile/v2`
- `0x180022b9e`: `http://www.microsoft.com/networking/WLAN/profile/v2`
- `0x180022a9d`: `SSIDBinaryList`
- `0x180022b00`: `SSIDPrefix`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall XwpGenerateSSIDConfig(
        struct _DOT11_AC_PROFILE *a1,
        struct IXMLDOMDocument2 *a2,
        struct IXMLDOMNode *a3)
{
  struct _DOT11_AC_PROFILE *v4; // r12
  struct IXMLDOMNode *v5; // rsi
  unsigned int v6; // edi
  struct IXMLDOMNode *v7; // rbx
  unsigned int v8; // edx
  unsigned int v9; // ecx
  unsigned int v10; // r15d
  __int64 v11; // rax
  _DWORD *v12; // r14
  unsigned int v13; // r15d
  SIZE_T v14; // rsi
  HANDLE ProcessHeap; // rax
  unsigned __int16 *v16; // r14
  int v17; // r10d
  unsigned int v18; // r11d
  _DWORD *v19; // r9
  __int16 v20; // cx
  __int64 v21; // r10
  __int16 v22; // cx
  HANDLE v23; // rax
  __int64 v24; // rax
  struct IXMLDOMNode *v25; // rcx
  unsigned int v26; // r15d
  __int64 v27; // rdx
  DWORD LastError; // eax
  unsigned int v30; // r14d
  unsigned int i; // r8d
  int v32; // ecx
  unsigned __int8 *v33; // r12
  unsigned int v34; // r15d
  unsigned int v35; // r8d
  __int64 v36; // rdx
  __int64 v37; // rcx
  rsize_t v38; // r9
  __int64 v39; // r14
  __int64 v40; // rax
  struct IXMLDOMNode **v41; // [rsp+28h] [rbp-91h]
  struct IXMLDOMNode **v42; // [rsp+30h] [rbp-89h]
  unsigned int v43; // [rsp+40h] [rbp-79h] BYREF
  unsigned int v44; // [rsp+44h] [rbp-75h]
  int v45; // [rsp+48h] [rbp-71h]
  struct IXMLDOMNode *v46; // [rsp+50h] [rbp-69h] BYREF
  unsigned int v47; // [rsp+58h] [rbp-61h]
  struct IXMLDOMNode *v48; // [rsp+60h] [rbp-59h] BYREF
  _DWORD *v49; // [rsp+68h] [rbp-51h]
  struct _DOT11_AC_PROFILE *v50; // [rsp+70h] [rbp-49h]
  unsigned __int16 v51[40]; // [rsp+80h] [rbp-39h] BYREF

  v4 = a1;
  v50 = a1;
  v48 = 0;
  v5 = 0;
  v46 = 0;
  v6 = XcAddChildElement(a2, a3, L"SSIDConfig", L"http://www.microsoft.com/networking/WLAN/profile/v1", 0, &v48);
  v7 = v48;
  if ( v6 )
    goto LABEL_32;
  v8 = *(_DWORD *)(*((_QWORD *)v4 + 1) + 4LL);
  v9 = v8;
  if ( v8 > 0x100 )
    v9 = 1;
  v44 = v9;
  v10 = v8 - 1;
  if ( v8 <= 0x100 )
    v10 = 0;
  v47 = v10;
  v11 = 0;
  while ( 1 )
  {
    v45 = v11;
    if ( (unsigned int)v11 >= v9 )
      break;
    v12 = (_DWORD *)(*((_QWORD *)v4 + 1) + 4 * (9 * v11 + 3));
    v49 = v12;
    if ( (unsigned int)(*v12 - 1) > 0x1F )
      goto LABEL_66;
    v6 = XcAddChildElement(a2, v7, L"SSID", L"http://www.microsoft.com/networking/WLAN/profile/v1", 0, &v46);
    if ( v6 )
    {
LABEL_65:
      v5 = v46;
      goto LABEL_32;
    }
    v13 = *v12;
    v14 = 2LL * (unsigned int)(2 * *v12 + 1);
    if ( v14 )
    {
      ProcessHeap = GetProcessHeap();
      v16 = (unsigned __int16 *)HeapAlloc(ProcessHeap, v6 + 8, v14);
      if ( !v16 )
        v6 += 8;
    }
    else
    {
      v16 = 0;
      v6 = 87;
    }
    SetLastError(v6);
    v5 = v46;
    if ( v16 )
    {
      v17 = 0;
      v18 = 0;
      if ( v13 )
      {
        v19 = v49;
        do
        {
          v20 = *((_BYTE *)v19 + v18 + 4) >> 4;
          v16[v17] = v20 + 55 + ((unsigned __int8)v20 < 0xAu ? 0xFFF9 : 0);
          v21 = (unsigned int)(v17 + 1);
          v22 = *((_BYTE *)v19 + v18 + 4) & 0xF;
          v16[v21] = v22 + ((unsigned __int8)v22 < 0xAu ? 48 : 55);
          v17 = v21 + 1;
          ++v18;
        }
        while ( v18 < v13 );
      }
      v16[v17] = 0;
      v6 = XcAddChildElement(a2, v5, L"hex", L"http://www.microsoft.com/networking/WLAN/profile/v1", v16, 0);
      v23 = GetProcessHeap();
      if ( !HeapFree(v23, 0, v16) )
      {
        LastError = GetLastError();
        SetLastError(LastError);
      }
    }
    else
    {
      v6 = GetLastError();
    }
    if ( v6 )
      goto LABEL_32;
    v43 = 33;
    if ( !(unsigned int)WlanUtf8SsidToDisplayName(v49, 0, v51, &v43) )
    {
      v24 = -1;
      do
        ++v24;
      while ( v51[v24] );
      if ( (unsigned __int64)(v24 - 1) <= 0xFE )
        XcAddChildElement(a2, v5, L"name", L"http://www.microsoft.com/networking/WLAN/profile/v1", v51, 0);
    }
    v25 = v5;
    if ( v5 )
    {
      v5 = 0;
      v46 = 0;
      ((void (__fastcall *)(struct IXMLDOMNode *))v25->lpVtbl->Release)(v25);
    }
    v11 = (unsigned int)(v45 + 1);
    v9 = v44;
  }
  if ( (*((_BYTE *)v4 + 4) & 4) != 0 )
  {
    v6 = XcAddChildElementBoolean(
           a2,
           v7,
           L"nonBroadcast",
           L"http://www.microsoft.com/networking/WLAN/profile/v1",
           (*((_DWORD *)v4 + 6) >> 1) & 1,
           v41);
    if ( v6 )
      goto LABEL_32;
    v9 = v44;
  }
  if ( v47 )
  {
    v30 = 0;
    for ( i = 0; i < v47; ++i )
    {
      v32 = *(_DWORD *)(*((_QWORD *)v4 + 1) + 36LL * (v9 + i) + 12);
      if ( (unsigned int)(v32 - 1) > 0x1F )
        goto LABEL_66;
      v30 += v32 + 1;
      v9 = v44;
    }
    v33 = (unsigned __int8 *)Xc_Process_user_allocate(v30);
    v34 = 0;
    if ( !v33 )
    {
      v6 = 14;
      goto LABEL_32;
    }
    v35 = 0;
    while ( v34 < v47 && v35 < v30 )
    {
      v36 = 9LL * (v34 + v44);
      v37 = *((_QWORD *)v50 + 1);
      v38 = *(unsigned int *)(v37 + 36LL * (v34 + v44) + 12);
      v45 = v38;
      v33[v35] = v38;
      v43 = v35 + 1;
      v6 = memcpy_s(&v33[v43], v30 - v43, (const void *const)(v37 + 16 + 4 * v36), v38);
      if ( v6 )
        goto LABEL_32;
      v35 = v43 + v45;
      ++v34;
    }
    v6 = XcAddChildElementHexBinary(
           a2,
           v7,
           L"SSIDBinaryList",
           L"http://www.microsoft.com/networking/WLAN/profile/v2",
           v33,
           v30,
           v42);
    v26 = 0;
    if ( v6 )
      goto LABEL_32;
    v4 = v50;
  }
  else
  {
    v26 = 0;
  }
  v27 = *((_QWORD *)v4 + 5);
  if ( v27 && *(_DWORD *)(v27 + 4) )
  {
    while ( 1 )
    {
      v39 = v27 + 36LL * v26;
      if ( (unsigned int)(*(_DWORD *)(v39 + 12) - 1) > 0x1F )
        break;
      v6 = XcAddChildElement(a2, v7, L"SSIDPrefix", L"http://www.microsoft.com/networking/WLAN/profile/v2", 0, &v46);
      if ( v6 )
        goto LABEL_65;
      v5 = v46;
      v6 = XcAddChildElementHexBinary(
             a2,
             v46,
             L"hex",
             L"http://www.microsoft.com/networking/WLAN/profile/v2",
             (unsigned __int8 *)(v39 + 16),
             *(_DWORD *)(v39 + 12),
             v42);
      if ( v6 )
        goto LABEL_32;
      v43 = 33;
      if ( !(unsigned int)WlanUtf8SsidToDisplayName(v39 + 12, 0, v51, &v43) )
      {
        v40 = -1;
        do
          ++v40;
        while ( v51[v40] );
        if ( (unsigned __int64)(v40 - 1) <= 0xFE )
          XcAddChildElement(a2, v5, L"name", L"http://www.microsoft.com/networking/WLAN/profile/v2", v51, 0);
      }
      ATL::CComPtrBase<IXMLDOMNode>::Release(&v46);
      ++v26;
      v27 = *((_QWORD *)v4 + 5);
      if ( v26 >= *(_DWORD *)(v27 + 4) )
        goto LABEL_65;
      v5 = v46;
    }
LABEL_66:
    v6 = 1206;
  }
LABEL_32:
  if ( v5 )
    ((void (__fastcall *)(struct IXMLDOMNode *))v5->lpVtbl->Release)(v5);
  if ( v7 )
    ((void (__fastcall *)(struct IXMLDOMNode *))v7->lpVtbl->Release)(v7);
  return v6;
}

```

## disassembly

```asm
0x18002263c  mov     [rsp-8+arg_18], rbx
0x180022641  push    rbp
0x180022642  push    rsi
0x180022643  push    rdi
0x180022644  push    r12
0x180022646  push    r13
0x180022648  push    r14
0x18002264a  push    r15
0x18002264c  lea     rbp, [rsp-27h]
0x180022651  sub     rsp, 0E0h
0x180022658  mov     rax, cs:__security_cookie
0x18002265f  xor     rax, rsp
0x180022662  mov     [rbp+57h+var_40], rax
0x180022666  mov     rax, r8
0x180022669  mov     r13, rdx
0x18002266c  mov     r12, rcx
0x18002266f  mov     [rbp+57h+var_A0], rcx
0x180022673  xor     r15d, r15d
0x180022676  mov     [rbp+57h+var_B0], r15
0x18002267a  mov     esi, r15d
0x18002267d  mov     [rbp+57h+var_C0], r15
0x180022681  lea     rcx, [rbp+57h+var_B0]
0x180022685  mov     [rsp+110h+var_E8], rcx; struct IXMLDOMNode **
0x18002268a  mov     [rsp+110h+var_F0], r15; unsigned __int16 *
0x18002268f  lea     r9, aHttpWwwMicroso_7; "http://www.microsoft.com/networking/WLA"...
0x180022696  lea     r8, aSsidconfig; "SSIDConfig"
0x18002269d  mov     rdx, rax; struct IXMLDOMNode *
0x1800226a0  mov     rcx, r13; struct IXMLDOMDocument2 *
0x1800226a3  call    ?XcAddChildElement@@YAKPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEBG22PEAPEAU2@@Z; XcAddChildElement(IXMLDOMDocument2 *,IXMLDOMNode *,ushort const *,ushort const *,ushort const *,IXMLDOMNode * *)
0x1800226a8  mov     edi, eax
0x1800226aa  mov     rbx, [rbp+57h+var_B0]
0x1800226ae  test    eax, eax
0x1800226b0  jnz     loc_1800228E9
0x1800226b6  mov     rcx, [r12+8]
0x1800226bb  mov     edx, [rcx+4]
0x1800226be  mov     ecx, edx
0x1800226c0  lea     r9d, [r15+1]
0x1800226c4  mov     r8d, 100h
0x1800226ca  cmp     edx, r8d
0x1800226cd  cmova   ecx, r9d
0x1800226d1  mov     [rbp+57h+var_CC], ecx
0x1800226d4  lea     r15d, [rdx-1]
0x1800226d8  cmp     edx, r8d
0x1800226db  cmovbe  r15d, eax
0x1800226df  mov     [rbp+57h+var_B8], r15d
0x1800226e3  xor     r15d, r15d
0x1800226e6  mov     eax, r15d
0x1800226e9  mov     [rbp+57h+var_C8], eax
0x1800226ec  cmp     eax, ecx
0x1800226ee  jnb     loc_1800228BD
0x1800226f4  lea     r14, [rax+rax*8]
0x1800226f8  mov     rax, [r12+8]
0x1800226fd  lea     r14, [r14+3]
0x180022701  lea     r14, [rax+r14*4]
0x180022705  mov     [rbp+57h+var_A8], r14
0x180022709  mov     eax, [r14]
0x18002270c  sub     eax, r9d
0x18002270f  cmp     eax, 1Fh
0x180022712  ja      loc_180022BE0
0x180022718  lea     rax, [rbp+57h+var_C0]
0x18002271c  mov     [rsp+110h+var_E8], rax; struct IXMLDOMNode **
0x180022721  mov     [rsp+110h+var_F0], r15; unsigned __int16 *
0x180022726  lea     r9, aHttpWwwMicroso_7; "http://www.microsoft.com/networking/WLA"...
0x18002272d  lea     r8, aSsid; "SSID"
0x180022734  mov     rdx, rbx; struct IXMLDOMNode *
0x180022737  mov     rcx, r13; struct IXMLDOMDocument2 *
0x18002273a  call    ?XcAddChildElement@@YAKPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEBG22PEAPEAU2@@Z; XcAddChildElement(IXMLDOMDocument2 *,IXMLDOMNode *,ushort const *,ushort const *,ushort const *,IXMLDOMNode * *)
0x18002273f  mov     edi, eax
0x180022741  test    eax, eax
0x180022743  jnz     loc_180022BD7
0x180022749  mov     r15d, [r14]
0x18002274c  lea     esi, ds:1[r15*2]
0x180022754  add     rsi, rsi
0x180022757  jz      loc_1800229A5
0x18002275d  call    cs:__imp_GetProcessHeap
0x180022763  mov     rcx, rax; hHeap
0x180022766  mov     r8, rsi; dwBytes
0x180022769  lea     esi, [rdi+8]
0x18002276c  mov     edx, esi; dwFlags
0x18002276e  call    cs:__imp_HeapAlloc
0x180022774  mov     r14, rax
0x180022777  test    rax, rax
0x18002277a  cmovz   edi, esi
0x18002277d  mov     ecx, edi; dwErrCode
0x18002277f  call    cs:__imp_SetLastError
0x180022785  mov     rsi, [rbp+57h+var_C0]
0x180022789  xor     eax, eax
0x18002278b  test    r14, r14
0x18002278e  jz      loc_1800229B1
0x180022794  mov     r10d, eax
0x180022797  mov     r11d, eax
0x18002279a  test    r15d, r15d
0x18002279d  jz      short loc_1800227FA
0x18002279f  mov     r9, [rbp+57h+var_A8]
0x1800227a3  mov     di, 0FFF9h
0x1800227a7  mov     r8d, r11d
0x1800227aa  mov     al, [r8+r9+4]
0x1800227af  shr     al, 4
0x1800227b2  movzx   ecx, al
0x1800227b5  cmp     cl, 0Ah
0x1800227b8  sbb     dx, dx
0x1800227bb  and     dx, di
0x1800227be  add     cx, 37h ; '7'
0x1800227c2  add     dx, cx
0x1800227c5  mov     eax, r10d
0x1800227c8  mov     [r14+rax*2], dx
0x1800227cd  inc     r10d
0x1800227d0  mov     al, [r8+r9+4]
0x1800227d5  and     al, 0Fh
0x1800227d7  movzx   ecx, al
0x1800227da  cmp     cl, 0Ah
0x1800227dd  sbb     ax, ax
0x1800227e0  and     ax, di
0x1800227e3  add     ax, 37h ; '7'
0x1800227e7  add     ax, cx
0x1800227ea  mov     [r14+r10*2], ax
0x1800227ef  inc     r10d
0x1800227f2  inc     r11d
0x1800227f5  cmp     r11d, r15d
0x1800227f8  jb      short loc_1800227A7
0x1800227fa  mov     ecx, r10d
0x1800227fd  xor     r15d, r15d
0x180022800  mov     [r14+rcx*2], r15w
0x180022805  mov     [rsp+110h+var_E8], r15; struct IXMLDOMNode **
0x18002280a  mov     [rsp+110h+var_F0], r14; unsigned __int16 *
0x18002280f  lea     r9, aHttpWwwMicroso_7; "http://www.microsoft.com/networking/WLA"...
0x180022816  lea     r8, aHex; "hex"
0x18002281d  mov     rdx, rsi; struct IXMLDOMNode *
0x180022820  mov     rcx, r13; struct IXMLDOMDocument2 *
0x180022823  call    ?XcAddChildElement@@YAKPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEBG22PEAPEAU2@@Z; XcAddChildElement(IXMLDOMDocument2 *,IXMLDOMNode *,ushort const *,ushort const *,ushort const *,IXMLDOMNode * *)
0x180022828  mov     edi, eax
0x18002282a  call    cs:__imp_GetProcessHeap
0x180022830  mov     rcx, rax; hHeap
0x180022833  mov     r8, r14; lpMem
0x180022836  xor     edx, edx; dwFlags
0x180022838  call    cs:__imp_HeapFree
0x18002283e  test    eax, eax
0x180022840  jz      loc_1800229C1
0x180022846  test    edi, edi
0x180022848  jnz     loc_1800228E9
0x18002284e  mov     [rbp+57h+var_D0], 21h ; '!'
0x180022855  lea     r9, [rbp+57h+var_D0]
0x180022859  lea     r8, [rbp+57h+var_90]
0x18002285d  xor     edx, edx
0x18002285f  mov     rcx, [rbp+57h+var_A8]
0x180022863  call    WlanUtf8SsidToDisplayName
0x180022868  test    eax, eax
0x18002286a  jnz     short loc_18002288D
0x18002286c  lea     rcx, [rbp+57h+var_90]
0x180022870  or      rax, 0FFFFFFFFFFFFFFFFh
0x180022874  inc     rax
0x180022877  cmp     [rcx+rax*2], r15w
0x18002287c  jnz     short loc_180022874
0x18002287e  dec     rax
0x180022881  cmp     rax, 0FEh
0x180022887  jbe     loc_18002293C
0x18002288d  mov     rcx, rsi
0x180022890  test    rsi, rsi
0x180022893  jz      short loc_1800228A9
0x180022895  mov     rsi, r15
0x180022898  mov     [rbp+57h+var_C0], r15
0x18002289c  mov     rax, [rcx]
0x18002289f  mov     rax, [rax+10h]
0x1800228a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800228a8  nop
0x1800228a9  mov     eax, [rbp+57h+var_C8]
0x1800228ac  mov     r9d, 1
0x1800228b2  add     eax, r9d
0x1800228b5  mov     ecx, [rbp+57h+var_CC]
0x1800228b8  jmp     loc_1800226E9
0x1800228bd  test    byte ptr [r12+4], 4
0x1800228c3  jnz     loc_180022968
0x1800228c9  mov     r15d, [rbp+57h+var_B8]
0x1800228cd  xor     eax, eax
0x1800228cf  test    r15d, r15d
0x1800228d2  jnz     loc_1800229D4
0x1800228d8  xor     r15d, r15d
0x1800228db  mov     rdx, [r12+28h]
0x1800228e0  test    rdx, rdx
0x1800228e3  jnz     loc_180022AC5
0x1800228e9  test    rsi, rsi
0x1800228ec  jz      short loc_1800228FE
0x1800228ee  mov     rax, [rsi]
0x1800228f1  mov     rcx, rsi
0x1800228f4  mov     rax, [rax+10h]
0x1800228f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800228fd  nop
0x1800228fe  test    rbx, rbx
0x180022901  jz      short loc_180022913
0x180022903  mov     rax, [rbx]
0x180022906  mov     rcx, rbx
0x180022909  mov     rax, [rax+10h]
0x18002290d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022912  nop
0x180022913  mov     eax, edi
0x180022915  mov     rcx, [rbp+57h+var_40]
0x180022919  xor     rcx, rsp; StackCookie
0x18002291c  call    __security_check_cookie
0x180022921  mov     rbx, [rsp+110h+arg_18]
0x180022929  add     rsp, 0E0h
0x180022930  pop     r15
0x180022932  pop     r14
0x180022934  pop     r13
0x180022936  pop     r12
0x180022938  pop     rdi
0x180022939  pop     rsi
0x18002293a  pop     rbp
0x18002293b  retn
0x18002293c  mov     [rsp+110h+var_E8], r15; struct IXMLDOMNode **
0x180022941  lea     rax, [rbp+57h+var_90]
0x180022945  mov     [rsp+110h+var_F0], rax; unsigned __int16 *
0x18002294a  lea     r9, aHttpWwwMicroso_7; "http://www.microsoft.com/networking/WLA"...
0x180022951  lea     r8, aName_1; "name"
0x180022958  mov     rdx, rsi; struct IXMLDOMNode *
0x18002295b  mov     rcx, r13; struct IXMLDOMDocument2 *
0x18002295e  call    ?XcAddChildElement@@YAKPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEBG22PEAPEAU2@@Z; XcAddChildElement(IXMLDOMDocument2 *,IXMLDOMNode *,ushort const *,ushort const *,ushort const *,IXMLDOMNode * *)
0x180022963  jmp     loc_18002288D
0x180022968  mov     eax, [r12+18h]
0x18002296d  shr     eax, 1
0x18002296f  and     eax, r9d
0x180022972  mov     dword ptr [rsp+110h+var_F0], eax; int
0x180022976  lea     r9, aHttpWwwMicroso_7; "http://www.microsoft.com/networking/WLA"...
0x18002297d  lea     r8, aNonbroadcast; "nonBroadcast"
0x180022984  mov     rdx, rbx; struct IXMLDOMNode *
0x180022987  mov     rcx, r13; struct IXMLDOMDocument2 *
0x18002298a  call    ?XcAddChildElementBoolean@@YAKPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEBG2HPEAPEAU2@@Z; XcAddChildElementBoolean(IXMLDOMDocument2 *,IXMLDOMNode *,ushort const *,ushort const *,int,IXMLDOMNode * *)
0x18002298f  mov     edi, eax
0x180022991  test    eax, eax
0x180022993  jnz     loc_1800228E9
0x180022999  mov     ecx, [rbp+57h+var_CC]
0x18002299c  lea     r9d, [rax+1]
0x1800229a0  jmp     loc_1800228C9
0x1800229a5  xor     r14d, r14d
0x1800229a8  lea     edi, [r14+57h]
0x1800229ac  jmp     loc_18002277D
0x1800229b1  call    cs:__imp_GetLastError
0x1800229b7  mov     edi, eax
0x1800229b9  xor     r15d, r15d
0x1800229bc  jmp     loc_180022846
0x1800229c1  call    cs:__imp_GetLastError
0x1800229c7  mov     ecx, eax; dwErrCode
0x1800229c9  call    cs:__imp_SetLastError
0x1800229cf  jmp     loc_180022846
0x1800229d4  mov     r14d, eax
0x1800229d7  mov     r8d, eax
0x1800229da  cmp     r8d, r15d
0x1800229dd  jnb     short loc_180022A09
0x1800229df  lea     eax, [rcx+r8]
0x1800229e3  lea     rdx, [rax+rax*8]
0x1800229e7  mov     rax, [r12+8]
0x1800229ec  mov     ecx, [rax+rdx*4+0Ch]
0x1800229f0  lea     eax, [rcx-1]
0x1800229f3  cmp     eax, 1Fh
0x1800229f6  ja      loc_180022BE0
0x1800229fc  inc     ecx
0x1800229fe  add     r14d, ecx
0x180022a01  add     r8d, r9d
0x180022a04  mov     ecx, [rbp+57h+var_CC]
0x180022a07  jmp     short loc_1800229DA
0x180022a09  mov     ecx, r14d; dwBytes
0x180022a0c  call    ?Xc_Process_user_allocate@@YAPEAX_K@Z; Xc_Process_user_allocate(unsigned __int64)
0x180022a11  mov     r12, rax
0x180022a14  xor     r15d, r15d
0x180022a17  test    rax, rax
0x180022a1a  jnz     short loc_180022A24
0x180022a1c  lea     edi, [rax+0Eh]
0x180022a1f  jmp     loc_1800228E9
0x180022a24  mov     r8d, r15d
0x180022a27  cmp     r15d, [rbp+57h+var_B8]
0x180022a2b  jnb     short loc_180022A8C
0x180022a2d  cmp     r8d, r14d
0x180022a30  jnb     short loc_180022A8C
0x180022a32  mov     eax, [rbp+57h+var_CC]
0x180022a35  add     eax, r15d
0x180022a38  lea     rdx, [rax+rax*8]
0x180022a3c  mov     rax, [rbp+57h+var_A0]
0x180022a40  mov     rcx, [rax+8]
0x180022a44  mov     r9d, [rcx+rdx*4+0Ch]; SourceSize
0x180022a49  mov     [rbp+57h+var_C8], r9d
0x180022a4d  mov     eax, r8d
0x180022a50  mov     [rax+r12], r9b
0x180022a54  lea     r10d, [r8+1]
0x180022a58  mov     [rbp+57h+var_D0], r10d
0x180022a5c  lea     r8, [rcx+10h]
0x180022a60  lea     r8, [r8+rdx*4]; Source
0x180022a64  mov     edx, r14d
0x180022a67  sub     edx, r10d; DestinationSize
0x180022a6a  mov     ecx, r10d
0x180022a6d  add     rcx, r12; Destination
0x180022a70  call    memcpy_s
0x180022a75  mov     edi, eax
0x180022a77  test    eax, eax
0x180022a79  jnz     loc_1800228E9
0x180022a7f  mov     r8d, [rbp+57h+var_C8]
0x180022a83  add     r8d, [rbp+57h+var_D0]
0x180022a87  inc     r15d
0x180022a8a  jmp     short loc_180022A27
0x180022a8c  mov     dword ptr [rsp+110h+var_E8], r14d; unsigned int
0x180022a91  mov     [rsp+110h+var_F0], r12; unsigned __int8 *
0x180022a96  lea     r9, aHttpWwwMicroso_5; "http://www.microsoft.com/networking/WLA"...
  ... truncated ...
```
