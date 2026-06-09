# CMailUserProp::SaveChanges(ulong)

- ea: `0x18002d920`
- end: `0x18002e267`
- name: `?SaveChanges@CMailUserProp@@UEAAJK@Z`
- size: `2375`
- prototype: `__int64 __fastcall(struct IMAPIProp *this, unsigned int)`
- caller_count: `2`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x1800172a0`
- `0x18002e270`

## callees

- `0x1800189ec`
- `0x18002d920`
- `0x18002e3b4`
- `0x18002e5a0`
- `0x18002fe40`
- `0x180033a7c`
- `0x180033c88`
- `0x18003be68`
- `0x1800620ac`
- `0x180093010`

## import_xrefs

- `KERNEL32!lstrcmpiW` at `0x18002dd6e`
- `KERNEL32!lstrcmpiW` at `0x18002dd6e`
- `KERNEL32!LocalFree` at `0x18002e24b`
- `KERNEL32!LocalFree` at `0x18002e24b`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18002da14`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18002da14`
- `KERNEL32!CompareFileTime` at `0x18002df53`
- `KERNEL32!CompareFileTime` at `0x18002df53`

## pseudocode

```c
__int64 __fastcall CMailUserProp::SaveChanges(struct IMAPIProp *this, int a2)
{
  int v3; // ebx
  struct IMAPIPropVtbl *lpVtbl; // rcx
  struct IMAPIPropVtbl *v5; // rax
  struct ENTRYID *AddRef; // r8
  _DWORD *v7; // r10
  unsigned int v8; // edx
  __int64 i; // rcx
  __int64 v10; // rdx
  struct _SPropValue *v11; // r8
  int v12; // r12d
  unsigned int v13; // r13d
  unsigned int v14; // r14d
  int v15; // edx
  unsigned int j; // esi
  unsigned int v17; // eax
  struct _SPropValue *v18; // rax
  LONG v19; // eax
  unsigned int v20; // r15d
  struct IMAPIPropVtbl *v21; // rdx
  int v22; // esi
  unsigned int v23; // ebx
  __int64 v24; // rdx
  unsigned int k; // ecx
  int v26; // eax
  __int64 v27; // rsi
  bool v28; // zf
  struct _SPropValue *v29; // r9
  unsigned int v30; // ecx
  unsigned int v31; // r8d
  int v32; // esi
  unsigned int m; // ecx
  unsigned int v34; // ecx
  struct _SPropValue *v35; // rdx
  unsigned int v36; // eax
  struct _SPropValue *v37; // rdx
  void *v38; // rcx
  unsigned int v39; // edx
  unsigned int v40; // r11d
  unsigned int v41; // r9d
  unsigned int v42; // r10d
  __int64 v43; // r11
  LONG l; // ecx
  __int64 v45; // rdx
  __int64 v46; // rdx
  unsigned int n; // edx
  char v48; // si
  struct IMAPIPropVtbl *v49; // rcx
  LPVOID pv; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v52; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v53; // [rsp+4Ch] [rbp-B4h] BYREF
  struct _SPropValue *v54; // [rsp+50h] [rbp-B0h] BYREF
  LPSPropValue pProp; // [rsp+58h] [rbp-A8h] BYREF
  struct _SPropValue *v56; // [rsp+60h] [rbp-A0h] BYREF
  HLOCAL hMem[2]; // [rsp+68h] [rbp-98h] BYREF
  FILETIME FileTime1; // [rsp+78h] [rbp-88h] BYREF
  __int64 v59; // [rsp+80h] [rbp-80h] BYREF
  void *v60; // [rsp+88h] [rbp-78h] BYREF
  struct _SPropValue *v61; // [rsp+90h] [rbp-70h] BYREF
  struct _FILETIME SystemTimeAsFileTime[2]; // [rsp+98h] [rbp-68h] BYREF
  HLOCAL v63; // [rsp+A8h] [rbp-58h]
  FILETIME FileTime2; // [rsp+B0h] [rbp-50h] BYREF
  struct _SPropValue *v65; // [rsp+B8h] [rbp-48h] BYREF
  struct _SPropValue v66; // [rsp+C0h] [rbp-40h] BYREF
  __int128 v67; // [rsp+D8h] [rbp-28h] BYREF
  struct _SPropValue v68; // [rsp+E8h] [rbp-18h] BYREF
  unsigned int v69; // [rsp+150h] [rbp+50h] BYREF
  int v70; // [rsp+158h] [rbp+58h]
  unsigned int v71; // [rsp+160h] [rbp+60h] BYREF
  unsigned int v72; // [rsp+168h] [rbp+68h] BYREF

  v70 = a2;
  v69 = 0;
  pv = 0;
  v56 = 0;
  v54 = 0;
  v61 = 0;
  v60 = 0;
  v67 = 0;
  memset(&v66, 0, sizeof(v66));
  v53 = 0;
  v71 = 0;
  v72 = 0;
  v52 = 0;
  v59 = 0;
  *(_OWORD *)&SystemTimeAsFileTime[0].dwLowDateTime = 0;
  v63 = 0;
  *(_OWORD *)hMem = 0;
  FileTime1 = 0;
  FileTime2 = 0;
  if ( LODWORD(this[84].lpVtbl) == 1 )
  {
    v3 = -2147024891;
    goto LABEL_130;
  }
  if ( !this[83].lpVtbl[5].GetNamesFromIDs )
  {
LABEL_4:
    v3 = -2147221246;
    goto LABEL_130;
  }
  v3 = CMailUserProp::Validate((CMailUserProp *)this);
  if ( v3 >= 0 )
  {
    pProp = 0;
    if ( HrGetOneProp(this, 0x30080040u, &pProp) >= 0 )
    {
      FileTime1 = (FILETIME)pProp->Value.cur.int64;
      MAPIFreeBuffer(pProp);
    }
    SystemTimeAsFileTime[0].dwLowDateTime = 805830720;
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime[1]);
    if ( !FileTime1.dwLowDateTime && !FileTime1.dwHighDateTime )
      FileTime1 = SystemTimeAsFileTime[1];
    v3 = ((__int64 (__fastcall *)(struct IMAPIProp *, __int64, struct _FILETIME *, _QWORD))this->lpVtbl->SetProps)(
           this,
           1,
           SystemTimeAsFileTime,
           0);
    if ( v3 >= 0 )
    {
      lpVtbl = this[83].lpVtbl;
      if ( HIDWORD(lpVtbl[9].GetNamesFromIDs) )
      {
        v5 = this[82].lpVtbl;
        if ( v5 )
        {
          AddRef = (struct ENTRYID *)v5->AddRef;
          if ( AddRef )
          {
            if ( LODWORD(v5->QueryInterface) )
              AddFolderParentEIDToItem(
                (struct AddressBook *)lpVtbl,
                (unsigned int)v5->QueryInterface,
                AddRef,
                this,
                0,
                0);
          }
        }
      }
      v3 = ((__int64 (__fastcall *)(struct IMAPIProp *, __int64, void **))this->lpVtbl->GetPropList)(
             this,
             0x80000000LL,
             &v60);
      if ( v3 >= 0 )
      {
        v7 = v60;
        if ( v60 )
        {
          v8 = *(_DWORD *)v60;
          for ( i = 0; ; i = (unsigned int)(i + 1) )
          {
            if ( (unsigned int)i >= v8 )
              goto LABEL_26;
            if ( *((_DWORD *)v60 + i + 1) == 806027522 )
              break;
          }
          if ( (unsigned int)i < v8 - 1 )
          {
            do
            {
              v10 = (unsigned int)(i + 1);
              v7[i + 1] = v7[v10 + 1];
              v7 = v60;
              i = v10;
            }
            while ( (unsigned int)v10 < *(_DWORD *)v60 - 1 );
          }
          --*v7;
          v7 = v60;
        }
LABEL_26:
        v3 = ((__int64 (__fastcall *)(struct IMAPIProp *, _DWORD *, __int64, unsigned int *, LPVOID *))this->lpVtbl->GetProps)(
               this,
               v7,
               0x80000000LL,
               &v69,
               &pv);
        if ( v3 < 0 )
          goto LABEL_130;
        v11 = (struct _SPropValue *)pv;
        v12 = 0;
        v13 = -1;
        LODWORD(pProp) = 0;
        v14 = -1;
        v15 = 1;
        for ( j = 0; ; ++j )
        {
          if ( j >= v69 )
          {
            v20 = 0;
            if ( v15 && (BYTE4(this[84].lpVtbl) & 3) != 0 )
            {
              *(_QWORD *)&v67 = 0x3001001F00000004LL;
              v53 = 0;
              v21 = this[82].lpVtbl;
              *((_QWORD *)&v67 + 1) = &v11[v13];
              if ( (*(int (__fastcall **)(HRESULT (__stdcall *)(IMAPIProp *, LPSPropTagArray *, LPGUID, ULONG, ULONG *, LPMAPINAMEID **), struct IMAPIPropVtbl *, _QWORD, __int128 *, unsigned int *, __int64 *))(*(_QWORD *)this[83].lpVtbl[5].GetNamesFromIDs + 24LL))(
                     this[83].lpVtbl[5].GetNamesFromIDs,
                     v21,
                     0,
                     &v67,
                     &v53,
                     &v59) < 0
                || !v53 )
              {
LABEL_72:
                v11 = (struct _SPropValue *)pv;
                goto LABEL_73;
              }
              if ( (BYTE4(this[84].lpVtbl) & 1) != 0 && v14 != -1 )
              {
                v22 = 0;
                v23 = 0;
                while ( !v22 )
                {
                  if ( (*(int (__fastcall **)(HRESULT (__stdcall *)(IMAPIProp *, LPSPropTagArray *, LPGUID, ULONG, ULONG *, LPMAPINAMEID **), __int64, _QWORD, unsigned int *, struct _SPropValue **))(*(_QWORD *)this[83].lpVtbl[5].GetNamesFromIDs + 128LL))(
                         this[83].lpVtbl[5].GetNamesFromIDs,
                         v59 + 16LL * v23,
                         0,
                         &v71,
                         &v56) >= 0 )
                  {
                    v24 = v71;
                    if ( v71 )
                    {
                      if ( v56 )
                      {
                        for ( k = 0; k < v71; ++k )
                        {
                          if ( v56[k].ulPropTag == 805503007 )
                          {
                            v26 = lstrcmpiW(v56[k].Value.lpszW, *((LPCWSTR *)pv + 3 * v14 + 1));
                            v24 = v71;
                            if ( !v26 )
                            {
                              v22 = 1;
                              v20 = v23;
                            }
                            break;
                          }
                        }
                        (*(void (__fastcall **)(HRESULT (__stdcall *)(IMAPIProp *, LPSPropTagArray *, LPGUID, ULONG, ULONG *, LPMAPINAMEID **), __int64, struct _SPropValue **))(*(_QWORD *)this[83].lpVtbl[5].GetNamesFromIDs + 40LL))(
                          this[83].lpVtbl[5].GetNamesFromIDs,
                          v24,
                          &v56);
                      }
                    }
                  }
                  if ( ++v23 >= v53 )
                  {
                    if ( !v22 )
                      goto LABEL_72;
                    break;
                  }
                }
              }
              if ( (BYTE4(this[84].lpVtbl) & 4) != 0 )
              {
                v11 = (struct _SPropValue *)pv;
                v12 = 1;
                goto LABEL_73;
              }
              v3 = -2147219964;
              break;
            }
LABEL_73:
            if ( !LODWORD(hMem[0]) && v12 )
            {
              v27 = 16LL * v20;
              v3 = LocalCopySBinary(hMem, v27 + v59, v11);
              if ( v3 < 0 )
                break;
              v28 = (BYTE4(this[84].lpVtbl) & 8) == 0;
              v66.Value = *(union _PV *)hMem;
              v66.ulPropTag = 268370178;
              if ( v28 )
              {
                v72 = 1;
                v54 = &v66;
              }
              else
              {
                v3 = (*(__int64 (__fastcall **)(HRESULT (__stdcall *)(IMAPIProp *, LPSPropTagArray *, LPGUID, ULONG, ULONG *, LPMAPINAMEID **), __int64, _QWORD, unsigned int *, struct _SPropValue **))(*(_QWORD *)this[83].lpVtbl[5].GetNamesFromIDs + 128LL))(
                       this[83].lpVtbl[5].GetNamesFromIDs,
                       v27 + v59,
                       0,
                       &v71,
                       &v56);
                if ( v3 < 0 )
                  break;
                v29 = v56;
                v30 = 0;
                v31 = v71;
                while ( v30 < v71 )
                {
                  if ( v56[v30].ulPropTag == 805830720 )
                  {
                    FileTime2 = (FILETIME)v56[v30].Value.cur.int64;
                    v56[v30].ulPropTag = 1;
                    v29 = v56;
                    v31 = v71;
                    break;
                  }
                  ++v30;
                }
                v3 = ScMergePropValues(1u, &v66, v31, v29, &v72, &v54);
                (*(void (__fastcall **)(HRESULT (__stdcall *)(IMAPIProp *, LPSPropTagArray *, LPGUID, ULONG, ULONG *, LPMAPINAMEID **), _QWORD, struct _SPropValue **))(*(_QWORD *)this[83].lpVtbl[5].GetNamesFromIDs + 40LL))(
                  this[83].lpVtbl[5].GetNamesFromIDs,
                  v71,
                  &v56);
                if ( v3 )
                  break;
              }
              v32 = 0;
              for ( m = 0; m < v69; ++m )
              {
                if ( *((_DWORD *)pv + 6 * m) == 268370178 )
                {
                  *((_DWORD *)pv + 6 * m) = 1;
                  break;
                }
              }
              if ( (BYTE4(this[84].lpVtbl) & 8) != 0 && CompareFileTime(&FileTime1, &FileTime2) < 0 )
              {
                v32 = 1;
                v34 = v69;
                v35 = (struct _SPropValue *)pv;
                v69 = v72;
                pv = v54;
                v72 = v34;
                v54 = v35;
              }
              v3 = ScMergePropValues(v72, v54, v69, (struct _SPropValue *)pv, &v52, &v61);
              if ( v32 )
              {
                v36 = v72;
                v37 = (struct _SPropValue *)pv;
                v72 = v69;
                v38 = v54;
                pv = v54;
                v69 = v36;
                v54 = v37;
              }
              else
              {
                v38 = pv;
              }
              if ( v3 )
                break;
              MAPIFreeBuffer(v38);
              v11 = v61;
              pv = v61;
              v69 = v52;
              v61 = 0;
              v52 = 0;
            }
            v39 = 0;
            v40 = -1;
            v41 = -1;
            v42 = -1;
            if ( v69 )
            {
              do
              {
                switch ( v11[v39].ulPropTag )
                {
                  case 0xFF60102u:
                    v42 = v39;
                    break;
                  case 0xFF90102u:
                    v41 = v39;
                    break;
                  case 0xFFF0102u:
                    v40 = v39;
                    break;
                }
                ++v39;
              }
              while ( v39 < v69 );
              if ( v40 == -1 || (v43 = v40, (l = v11[v43].Value.l) == 0) )
              {
                if ( v41 != -1 )
                {
                  v11[v41].ulPropTag = 1;
                  v11 = (struct _SPropValue *)pv;
                }
                if ( v42 != -1 )
                {
                  v11[v42].ulPropTag = 1;
LABEL_117:
                  v11 = (struct _SPropValue *)pv;
                }
              }
              else
              {
                if ( v41 != -1 )
                {
                  v45 = v41;
                  v11[v45].Value.l = l;
                  *((_QWORD *)pv + v45 * 3 + 2) = *((_QWORD *)pv + v43 * 3 + 2);
                  v11 = (struct _SPropValue *)pv;
                }
                if ( v42 != -1 )
                {
                  v46 = v42;
                  v11[v46].Value.l = v11[v43].Value.l;
                  *((_QWORD *)pv + v46 * 3 + 2) = *((_QWORD *)pv + v43 * 3 + 2);
                  goto LABEL_117;
                }
              }
            }
            for ( n = 0; n < v69; ++n )
            {
              if ( v11[n].ulPropTag == 1 )
              {
                v65 = 0;
                memset(&v68, 0, sizeof(v68));
                v68.ulPropTag = 1;
                if ( ScMergePropValues(1u, &v68, v69, v11, &v52, &v65) < 0 )
                {
                  v11 = (struct _SPropValue *)pv;
                }
                else
                {
                  if ( pv )
                    FreeBufferAndNull(&pv);
                  v11 = v65;
                  pv = v65;
                  v69 = v52;
                }
                break;
              }
            }
            v48 = v70;
            v3 = (*(__int64 (__fastcall **)(HRESULT (__stdcall *)(IMAPIProp *, LPSPropTagArray *, LPGUID, ULONG, ULONG *, LPMAPINAMEID **), HLOCAL *, _QWORD, _QWORD, int, struct _SPropValue *))(*(_QWORD *)this[83].lpVtbl[5].GetNamesFromIDs + 152LL))(
                   this[83].lpVtbl[5].GetNamesFromIDs,
                   hMem,
                   (unsigned int)pProp,
                   v69,
                   v70 & 4,
                   v11);
            if ( v3 >= 0 )
            {
              v49 = this[78].lpVtbl;
              SystemTimeAsFileTime[1] = (struct _FILETIME)hMem[0];
              v63 = hMem[1];
              SystemTimeAsFileTime[0].dwLowDateTime = 268370178;
              v3 = (*((__int64 (__fastcall **)(struct IMAPIPropVtbl *, __int64, struct _FILETIME *, _QWORD))v49->QueryInterface
                    + 8))(
                     v49,
                     1,
                     SystemTimeAsFileTime,
                     0);
              if ( v3 >= 0 )
                LODWORD(this[84].lpVtbl) = ((v48 & 2) != 0) + 1;
            }
            break;
          }
          v17 = j;
          if ( v11[j].ulPropTag != 805371935 )
            v17 = v13;
          v13 = v17;
          if ( v11[j].ulPropTag == 805503007 )
          {
            v14 = j;
          }
          else if ( v11[j].ulPropTag == 268370178 )
          {
            v18 = &v11[j];
            if ( v18->Value.l && v11[j].Value.bin.lpb )
            {
              v3 = LocalCopySBinary(hMem, &v18->Value, v11);
              if ( v3 < 0 )
                break;
              if ( IsWABEntryID((unsigned int)hMem[0], (struct ENTRYID *)hMem[1], 0, 0, 0, 0, 0) == 4 )
                goto LABEL_4;
              v11 = (struct _SPropValue *)pv;
              v15 = 0;
              continue;
            }
            v18->Value.l = 0;
            v11 = (struct _SPropValue *)pv;
          }
          if ( v11[j].ulPropTag == 268304387 )
          {
            v19 = v11[j].Value.l;
            switch ( v19 )
            {
              case 4:
                LODWORD(pProp) = 3;
                break;
              case 6:
                LODWORD(pProp) = 1;
                break;
              case 8:
                LODWORD(pProp) = 2;
                break;
              default:
                v3 = -2147221240;
                goto LABEL_130;
            }
          }
        }
      }
    }
  }
LABEL_130:
  (*(void (__fastcall **)(HRESULT (__stdcall *)(IMAPIProp *, LPSPropTagArray *, LPGUID, ULONG, ULONG *, LPMAPINAMEID **), _QWORD, __int64))(*(_QWORD *)this[83].lpVtbl[5].GetNamesFromIDs + 56LL))(
    this[83].lpVtbl[5].GetNamesFromIDs,
    v53,
    v59);
  FreeBufferAndNull(&pv);
  FreeBufferAndNull(&v60);
  FreeBufferAndNull((void **)&v61);
  if ( (BYTE4(this[84].lpVtbl) & 8) != 0 )
    FreeBufferAndNull((void **)&v54);
  if ( hMem[1] )
    LocalFree(hMem[1]);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18002d920  mov     [rsp-8+arg_8], edx
0x18002d924  push    rbp
0x18002d925  push    rbx
0x18002d926  push    rsi
0x18002d927  push    rdi
0x18002d928  push    r12
0x18002d92a  push    r13
0x18002d92c  push    r14
0x18002d92e  push    r15
0x18002d930  lea     rbp, [rsp-8]
0x18002d935  sub     rsp, 108h
0x18002d93c  xor     r13d, r13d
0x18002d93f  xor     eax, eax
0x18002d941  xorps   xmm0, xmm0
0x18002d944  mov     [rbp+40h+arg_0], r13d
0x18002d948  xorps   xmm1, xmm1
0x18002d94b  mov     [rsp+140h+pv], r13
0x18002d950  mov     rdi, rcx
0x18002d953  mov     [rsp+140h+var_E0], r13
0x18002d958  lea     r15d, [r13+1]
0x18002d95c  mov     [rsp+140h+var_F0], r13
0x18002d961  mov     [rbp+40h+var_B0], r13
0x18002d965  mov     [rbp+40h+var_B8], r13
0x18002d969  movups  [rbp+40h+var_68], xmm0
0x18002d96d  mov     qword ptr [rbp+40h+var_80.Value+8], rax
0x18002d971  movups  xmmword ptr [rbp+40h+var_80.ulPropTag], xmm1
0x18002d975  mov     [rsp+140h+var_F4], r13d
0x18002d97a  mov     [rbp+40h+arg_10], r13d
0x18002d97e  mov     [rbp+40h+arg_18], r13d
0x18002d982  mov     [rsp+140h+var_F8], r13d
0x18002d987  mov     [rbp+40h+var_C0], r13
0x18002d98b  movups  xmmword ptr [rbp+40h+SystemTimeAsFileTime.dwLowDateTime], xmm0
0x18002d98f  mov     [rbp+40h+var_98], rax
0x18002d993  movups  xmmword ptr [rsp+140h+hMem], xmm0
0x18002d998  mov     qword ptr [rsp+140h+FileTime1.dwLowDateTime], r13
0x18002d99d  mov     qword ptr [rbp+40h+FileTime2.dwLowDateTime], r13
0x18002d9a1  cmp     [rcx+2A0h], r15d
0x18002d9a8  jnz     short loc_18002D9B4
0x18002d9aa  mov     ebx, 80070005h
0x18002d9af  jmp     loc_18002E1F0
0x18002d9b4  mov     rax, [rcx+298h]
0x18002d9bb  cmp     [rax+290h], r13
0x18002d9c2  jnz     short loc_18002D9CE
0x18002d9c4  mov     ebx, 80040102h
0x18002d9c9  jmp     loc_18002E1F0
0x18002d9ce  call    ?Validate@CMailUserProp@@IEAAJXZ; CMailUserProp::Validate(void)
0x18002d9d3  mov     ebx, eax
0x18002d9d5  test    eax, eax
0x18002d9d7  js      loc_18002E1F0
0x18002d9dd  mov     ebx, 30080040h
0x18002d9e2  mov     [rsp+140h+pProp], r13
0x18002d9e7  mov     edx, ebx; ulPropTag
0x18002d9e9  lea     r8, [rsp+140h+pProp]; lppProp
0x18002d9ee  mov     rcx, rdi; lpMapiProp
0x18002d9f1  call    HrGetOneProp
0x18002d9f6  test    eax, eax
0x18002d9f8  js      short loc_18002DA0D
0x18002d9fa  mov     rcx, [rsp+140h+pProp]; pv
0x18002d9ff  mov     rax, [rcx+8]
0x18002da03  mov     qword ptr [rsp+140h+FileTime1.dwLowDateTime], rax
0x18002da08  call    MAPIFreeBuffer
0x18002da0d  lea     rcx, [rbp+40h+SystemTimeAsFileTime.dwLowDateTime+8]; lpSystemTimeAsFileTime
0x18002da11  mov     [rbp+40h+SystemTimeAsFileTime.dwLowDateTime], ebx
0x18002da14  call    cs:__imp_GetSystemTimeAsFileTime
0x18002da1a  cmp     [rsp+140h+FileTime1.dwLowDateTime], r13d
0x18002da1f  jnz     short loc_18002DA31
0x18002da21  cmp     [rsp+140h+FileTime1.dwHighDateTime], r13d
0x18002da26  jnz     short loc_18002DA31
0x18002da28  mov     rax, qword ptr [rbp+40h+SystemTimeAsFileTime.dwLowDateTime+8]
0x18002da2c  mov     qword ptr [rsp+140h+FileTime1.dwLowDateTime], rax
0x18002da31  mov     rax, [rdi]
0x18002da34  lea     r8, [rbp+40h+SystemTimeAsFileTime]
0x18002da38  xor     r9d, r9d
0x18002da3b  mov     edx, r15d
0x18002da3e  mov     rcx, rdi
0x18002da41  mov     rax, [rax+40h]
0x18002da45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002da4a  mov     ebx, eax
0x18002da4c  test    eax, eax
0x18002da4e  js      loc_18002E1F0
0x18002da54  mov     rcx, [rdi+298h]; struct AddressBook *
0x18002da5b  cmp     [rcx+454h], r13d
0x18002da62  jz      short loc_18002DA91
0x18002da64  mov     rax, [rdi+290h]
0x18002da6b  test    rax, rax
0x18002da6e  jz      short loc_18002DA91
0x18002da70  mov     r8, [rax+8]; struct ENTRYID *
0x18002da74  test    r8, r8
0x18002da77  jz      short loc_18002DA91
0x18002da79  mov     edx, [rax]; unsigned int
0x18002da7b  test    edx, edx
0x18002da7d  jz      short loc_18002DA91
0x18002da7f  mov     [rsp+140h+var_118], r13; struct ENTRYID *
0x18002da84  mov     r9, rdi; struct IMAPIProp *
0x18002da87  mov     dword ptr [rsp+140h+var_120], r13d; unsigned int
0x18002da8c  call    ?AddFolderParentEIDToItem@@YAJPEAVAddressBook@@KPEAUENTRYID@@PEAUIMAPIProp@@K1@Z; AddFolderParentEIDToItem(AddressBook *,ulong,ENTRYID *,IMAPIProp *,ulong,ENTRYID *)
0x18002da91  mov     rax, [rdi]
0x18002da94  lea     r8, [rbp+40h+var_B8]
0x18002da98  mov     r14d, 80000000h
0x18002da9e  mov     rcx, rdi
0x18002daa1  mov     edx, r14d
0x18002daa4  mov     rax, [rax+30h]
0x18002daa8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002daad  mov     ebx, eax
0x18002daaf  test    eax, eax
0x18002dab1  js      loc_18002E1F0
0x18002dab7  mov     r10, [rbp+40h+var_B8]
0x18002dabb  or      esi, 0FFFFFFFFh
0x18002dabe  test    r10, r10
0x18002dac1  jz      short loc_18002DB08
0x18002dac3  mov     edx, [r10]
0x18002dac6  mov     ecx, r13d
0x18002dac9  cmp     ecx, edx
0x18002dacb  jnb     short loc_18002DB08
0x18002dacd  cmp     dword ptr [r10+rcx*4+4], 300B0102h
0x18002dad6  jz      short loc_18002DADD
0x18002dad8  add     ecx, r15d
0x18002dadb  jmp     short loc_18002DAC9
0x18002dadd  lea     eax, [rdx-1]
0x18002dae0  cmp     ecx, eax
0x18002dae2  jnb     short loc_18002DB01
0x18002dae4  lea     edx, [rcx+1]
0x18002dae7  mov     eax, [r10+rdx*4+4]
0x18002daec  mov     [r10+rcx*4+4], eax
0x18002daf1  mov     r10, [rbp+40h+var_B8]
0x18002daf5  mov     ecx, edx
0x18002daf7  mov     eax, [r10]
0x18002dafa  sub     eax, r15d
0x18002dafd  cmp     edx, eax
0x18002daff  jb      short loc_18002DAE4
0x18002db01  add     [r10], esi
0x18002db04  mov     r10, [rbp+40h+var_B8]
0x18002db08  mov     rax, [rdi]
0x18002db0b  lea     rcx, [rsp+140h+pv]
0x18002db10  mov     [rsp+140h+var_120], rcx
0x18002db15  lea     r9, [rbp+40h+arg_0]
0x18002db19  mov     r8d, r14d
0x18002db1c  mov     rdx, r10
0x18002db1f  mov     rcx, rdi
0x18002db22  mov     rax, [rax+28h]
0x18002db26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002db2b  mov     ebx, eax
0x18002db2d  test    eax, eax
0x18002db2f  js      loc_18002E1F0
0x18002db35  mov     r8, [rsp+140h+pv]
0x18002db3a  xor     r12d, r12d
0x18002db3d  mov     r13d, esi
0x18002db40  mov     dword ptr [rsp+140h+pProp], r12d
0x18002db45  mov     r14d, esi
0x18002db48  mov     edx, r15d
0x18002db4b  mov     esi, r12d
0x18002db4e  cmp     esi, [rbp+40h+arg_0]
0x18002db51  jnb     loc_18002DC37
0x18002db57  mov     eax, esi
0x18002db59  lea     rcx, [rax+rax*2]
0x18002db5d  mov     eax, esi
0x18002db5f  cmp     dword ptr [r8+rcx*8], 3001001Fh
0x18002db67  cmovnz  eax, r13d
0x18002db6b  cmp     dword ptr [r8+rcx*8], 3003001Fh
0x18002db73  mov     r13d, eax
0x18002db76  jnz     short loc_18002DB7D
0x18002db78  mov     r14d, esi
0x18002db7b  jmp     short loc_18002DBEE
0x18002db7d  cmp     dword ptr [r8+rcx*8], 0FFF0102h
0x18002db85  jnz     short loc_18002DBEE
0x18002db87  lea     rax, [r8+rcx*8]
0x18002db8b  cmp     [rax+8], r12d
0x18002db8f  jz      short loc_18002DBE5
0x18002db91  cmp     [r8+rcx*8+10h], r12
0x18002db96  jz      short loc_18002DBE5
0x18002db98  lea     rdx, [rax+8]
0x18002db9c  lea     rcx, [rsp+140h+hMem]
0x18002dba1  call    _LocalCopySBinary
0x18002dba6  mov     ebx, eax
0x18002dba8  test    eax, eax
0x18002dbaa  js      loc_18002E1F0
0x18002dbb0  mov     rdx, [rsp+140h+hMem+8]; struct ENTRYID *
0x18002dbb5  xor     r9d, r9d; void **
0x18002dbb8  mov     ecx, dword ptr [rsp+140h+hMem]; unsigned int
0x18002dbbc  xor     r8d, r8d; void **
0x18002dbbf  mov     [rsp+140h+var_110], r12; unsigned int *
0x18002dbc4  mov     [rsp+140h+var_118], r12; unsigned int *
0x18002dbc9  mov     [rsp+140h+var_120], r12; void **
0x18002dbce  call    ?IsWABEntryID@@YAEKPEAUENTRYID@@PEAPEAX11PEAK2@Z; IsWABEntryID(ulong,ENTRYID *,void * *,void * *,void * *,ulong *,ulong *)
0x18002dbd3  cmp     al, 4
0x18002dbd5  jz      loc_18002D9C4
0x18002dbdb  mov     r8, [rsp+140h+pv]
0x18002dbe0  mov     edx, r12d
0x18002dbe3  jmp     short loc_18002DC25
0x18002dbe5  mov     [rax+8], r12d
0x18002dbe9  mov     r8, [rsp+140h+pv]
0x18002dbee  cmp     dword ptr [r8+rcx*8], 0FFE0003h
0x18002dbf6  jnz     short loc_18002DC25
0x18002dbf8  mov     eax, [r8+rcx*8+8]
0x18002dbfd  cmp     eax, 4
0x18002dc00  jz      short loc_18002DC1D
0x18002dc02  cmp     eax, 6
0x18002dc05  jz      short loc_18002DC16
0x18002dc07  cmp     eax, 8
0x18002dc0a  jnz     short loc_18002DC2D
0x18002dc0c  mov     dword ptr [rsp+140h+pProp], 2
0x18002dc14  jmp     short loc_18002DC25
0x18002dc16  mov     dword ptr [rsp+140h+pProp], r15d
0x18002dc1b  jmp     short loc_18002DC25
0x18002dc1d  mov     dword ptr [rsp+140h+pProp], 3
0x18002dc25  add     esi, r15d
0x18002dc28  jmp     loc_18002DB4E
0x18002dc2d  mov     ebx, 80040108h
0x18002dc32  jmp     loc_18002E1F0
0x18002dc37  mov     r15d, r12d
0x18002dc3a  test    edx, edx
0x18002dc3c  jz      loc_18002DDDA
0x18002dc42  test    byte ptr [rdi+2A4h], 3
0x18002dc49  jz      loc_18002DDDA
0x18002dc4f  mov     eax, r13d
0x18002dc52  lea     rdx, [rbp+40h+var_C0]
0x18002dc56  mov     [rsp+140h+var_118], rdx
0x18002dc5b  lea     r9, [rbp+40h+var_68]
0x18002dc5f  mov     dword ptr [rbp+40h+var_68], 4
0x18002dc66  lea     rdx, [rsp+140h+var_F4]
0x18002dc6b  mov     dword ptr [rbp+40h+var_68+4], 3001001Fh
0x18002dc72  xor     r13d, r13d
0x18002dc75  lea     rcx, [rax+rax*2]
0x18002dc79  mov     [rsp+140h+var_F4], r13d
0x18002dc7e  lea     rax, [r8+rcx*8]
0x18002dc82  mov     [rsp+140h+var_120], rdx
0x18002dc87  mov     rdx, [rdi+290h]
0x18002dc8e  xor     r8d, r8d
0x18002dc91  mov     qword ptr [rbp+40h+var_68+8], rax
0x18002dc95  mov     rax, [rdi+298h]
0x18002dc9c  mov     rcx, [rax+290h]
0x18002dca3  mov     rax, [rcx]
0x18002dca6  mov     rax, [rax+18h]
0x18002dcaa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002dcaf  test    eax, eax
0x18002dcb1  js      loc_18002DDD3
0x18002dcb7  mov     eax, [rsp+140h+var_F4]
0x18002dcbb  test    eax, eax
0x18002dcbd  jz      loc_18002DDD3
0x18002dcc3  test    byte ptr [rdi+2A4h], 1
0x18002dcca  jz      loc_18002DDB0
0x18002dcd0  cmp     r14d, 0FFFFFFFFh
0x18002dcd4  jz      loc_18002DDB0
0x18002dcda  mov     esi, r13d
0x18002dcdd  mov     ebx, r13d
0x18002dce0  test    eax, eax
0x18002dce2  jz      loc_18002DDD3
0x18002dce8  test    esi, esi
0x18002dcea  jnz     loc_18002DDB0
0x18002dcf0  mov     rax, [rdi+298h]
0x18002dcf7  lea     r8, [rsp+140h+var_E0]
0x18002dcfc  mov     [rsp+140h+var_120], r8
0x18002dd01  lea     r9, [rbp+40h+arg_10]
0x18002dd05  mov     edx, ebx
0x18002dd07  xor     r8d, r8d
0x18002dd0a  shl     rdx, 4
0x18002dd0e  mov     rcx, [rax+290h]
0x18002dd15  add     rdx, [rbp+40h+var_C0]
0x18002dd19  mov     rax, [rcx]
0x18002dd1c  mov     rax, [rax+80h]
0x18002dd23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002dd28  test    eax, eax
0x18002dd2a  js      short loc_18002DDA0
0x18002dd2c  mov     edx, [rbp+40h+arg_10]
0x18002dd2f  test    edx, edx
0x18002dd31  jz      short loc_18002DDA0
0x18002dd33  mov     r8, [rsp+140h+var_E0]
0x18002dd38  test    r8, r8
0x18002dd3b  jz      short loc_18002DDA0
0x18002dd3d  mov     ecx, r13d
0x18002dd40  cmp     ecx, edx
0x18002dd42  jnb     short loc_18002DD81
0x18002dd44  mov     eax, ecx
0x18002dd46  lea     r9, [rax+rax*2]
0x18002dd4a  cmp     dword ptr [r8+r9*8], 3003001Fh
0x18002dd52  jz      short loc_18002DD58
0x18002dd54  inc     ecx
0x18002dd56  jmp     short loc_18002DD40
0x18002dd58  mov     rdx, [rsp+140h+pv]
0x18002dd5d  mov     eax, r14d
0x18002dd60  lea     rcx, [rax+rax*2]
0x18002dd64  mov     rdx, [rdx+rcx*8+8]; lpString2
0x18002dd69  mov     rcx, [r8+r9*8+8]; lpString1
0x18002dd6e  call    cs:__imp_lstrcmpiW
0x18002dd74  mov     edx, [rbp+40h+arg_10]
0x18002dd77  test    eax, eax
0x18002dd79  jnz     short loc_18002DD81
0x18002dd7b  lea     esi, [rax+1]
0x18002dd7e  mov     r15d, ebx
0x18002dd81  mov     rax, [rdi+298h]
0x18002dd88  lea     r8, [rsp+140h+var_E0]
0x18002dd8d  mov     rcx, [rax+290h]
0x18002dd94  mov     rax, [rcx]
0x18002dd97  mov     rax, [rax+28h]
0x18002dd9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002dda0  inc     ebx
0x18002dda2  cmp     ebx, [rsp+140h+var_F4]
0x18002dda6  jb      loc_18002DCE8
0x18002ddac  test    esi, esi
0x18002ddae  jz      short loc_18002DDD3
  ... truncated ...
```
