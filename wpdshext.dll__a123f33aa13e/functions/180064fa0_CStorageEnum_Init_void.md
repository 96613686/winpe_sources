# CStorageEnum::_Init(void)

- ea: `0x180064fa0`
- end: `0x1800654a8`
- name: `?_Init@CStorageEnum@@MEAAJXZ`
- size: `1288`
- prototype: `__int64 __fastcall(CStorageEnum *__hidden this)`
- caller_count: `0`
- callee_count: `18`
- tags: `broker_com_uri`

## callees

- `0x180004110`
- `0x180009890`
- `0x18000bde4`
- `0x18000cc48`
- `0x18000e760`
- `0x18001d6b0`
- `0x1800285c8`
- `0x1800287d0`
- `0x18002d020`
- `0x18002eda4`
- `0x18002ff5c`
- `0x180035590`
- `0x180039d74`
- `0x180055574`
- `0x1800555a4`
- `0x180064fa0`
- `0x18006b954`
- `0x180078010`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x1800652ab`
- `KERNEL32!EnterCriticalSection` at `0x1800652ab`
- `KERNEL32!LeaveCriticalSection` at `0x1800652c4`
- `KERNEL32!LeaveCriticalSection` at `0x1800652c4`
- `KERNEL32!CompareFileTime` at `0x180065354`
- `KERNEL32!CompareFileTime` at `0x180065354`
- `KERNEL32!GetSystemTime` at `0x180065162`
- `KERNEL32!GetSystemTime` at `0x180065162`
- `KERNEL32!SystemTimeToFileTime` at `0x180065171`
- `KERNEL32!SystemTimeToFileTime` at `0x180065171`
- `ole32!PropVariantClear` at `0x180065280`
- `ole32!PropVariantClear` at `0x180065432`
- `ole32!PropVariantClear` at `0x180065280`
- `ole32!PropVariantClear` at `0x180065432`
- `SHELL32!__imp_ILFree` at `0x180065246`
- `SHELL32!__imp_ILFree` at `0x1800653c3`
- `SHELL32!__imp_ILFree` at `0x180065246`
- `SHELL32!__imp_ILFree` at `0x1800653c3`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CStorageEnum::_Init(CStorageEnum *this)
{
  _QWORD *v2; // r14
  int v3; // ebx
  int v4; // eax
  _QWORD *v5; // rcx
  __int64 v6; // rdx
  __int64 v7; // r9
  unsigned int v8; // r15d
  CStorageFolder *v9; // rcx
  const struct STORAGEITEM *v10; // rax
  __int64 v11; // rdx
  CDeviceCache *v12; // rcx
  int v13; // r14d
  _QWORD *v14; // rcx
  __int64 v15; // rdx
  __int64 v16; // r9
  __int64 *v17; // r8
  struct DEVITEM_CACHE *Item; // r13
  int i; // esi
  _DWORD *v20; // rcx
  int v21; // eax
  const FILETIME *Ptr; // rax
  const FILETIME *v23; // r12
  int j; // r15d
  CDeviceCache *v25; // rcx
  int v26; // eax
  const ITEMIDLIST *v27; // rax
  ITEMIDLIST *v28; // r12
  LPITEMIDLIST pidl; // [rsp+30h] [rbp-D0h] BYREF
  int v31; // [rsp+38h] [rbp-C8h] BYREF
  struct IPortableDevice *v32; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v33; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v34; // [rsp+50h] [rbp-B0h] BYREF
  struct _FILETIME FileTime; // [rsp+58h] [rbp-A8h] BYREF
  LPITEMIDLIST v36; // [rsp+60h] [rbp-A0h] BYREF
  const FILETIME *v37; // [rsp+68h] [rbp-98h]
  PROPVARIANT pvar; // [rsp+70h] [rbp-90h] BYREF
  FILETIME FileTime1; // [rsp+88h] [rbp-78h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 v41[264]; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 v42[264]; // [rsp+2B0h] [rbp+1B0h] BYREF

  pidl = 0;
  v31 = 0;
  FileTime = 0;
  SystemTime = 0;
  v32 = 0;
  v34 = 0;
  v33 = 0;
  v2 = (_QWORD *)((char *)this + 32);
  if ( *((_QWORD *)this + 4) )
  {
    v3 = 0;
    goto LABEL_76;
  }
  memset(&pvar, 0, sizeof(pvar));
  if ( !(unsigned int)CDPA_Base<PROPERTY_ITEM>::Create((char *)this + 32) )
  {
    v3 = -2147024882;
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v6 = 12;
      v7 = 2147942414LL;
      goto LABEL_70;
    }
    goto LABEL_71;
  }
  v4 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int16 *, __int64))(**((_QWORD **)this + 2) + 96LL))(
         *((_QWORD *)this + 2),
         v41,
         260);
  v3 = v4;
  if ( v4 < 0 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v6 = 13;
LABEL_8:
      v7 = (unsigned int)v4;
LABEL_70:
      WPP_SF_d(v5[2], v6, WPP_6ba37b08510337949ff0d977e37e44c8_Traceguids, v7);
      goto LABEL_71;
    }
    goto LABEL_71;
  }
  v4 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, struct IPortableDevice **))(**((_QWORD **)this + 2) + 136LL))(
         *((_QWORD *)this + 2),
         *(_QWORD *)(*((_QWORD *)this + 2) + 64LL),
         &v32);
  v3 = v4;
  if ( v4 < 0 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v6 = 14;
      goto LABEL_8;
    }
LABEL_71:
    CDPA<_ITEMIDLIST __unaligned>::DestroyCallback(v2);
    PropVariantClear(&pvar);
    if ( v3 < 0 )
    {
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        v15 = 18;
        v16 = (unsigned int)v3;
        v17 = WPP_6ba37b08510337949ff0d977e37e44c8_Traceguids;
LABEL_75:
        WPP_SF_d(v14[2], v15, v17, v16);
      }
    }
    goto LABEL_76;
  }
  v4 = ((__int64 (__fastcall *)(struct IPortableDevice *, __int64 *))v32->lpVtbl->Capabilities)(v32, &v34);
  v3 = v4;
  if ( v4 < 0 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v6 = 15;
      goto LABEL_8;
    }
    goto LABEL_71;
  }
  v4 = (*(__int64 (__fastcall **)(__int64, const GUID *, __int64 *))(*(_QWORD *)v34 + 48LL))(
         v34,
         &WPD_FUNCTIONAL_CATEGORY_STORAGE,
         &v33);
  v3 = v4;
  if ( v4 < 0 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v6 = 16;
      goto LABEL_8;
    }
    goto LABEL_71;
  }
  v8 = 0;
  GetSystemTime(&SystemTime);
  SystemTimeToFileTime(&SystemTime, &FileTime);
  while ( !(*(unsigned int (__fastcall **)(__int64, _QWORD, PROPVARIANT *))(*(_QWORD *)v33 + 32LL))(v33, v8, &pvar) )
  {
    if ( pvar.vt != 31 )
    {
      v3 = -2147418113;
      goto LABEL_71;
    }
    if ( (int)CStorageFolder::_CreateIDList(*((CStorageFolder **)this + 2), v32, pvar.bstrVal, &pidl, &v31) >= 0 )
    {
      v10 = CStorageFolder::_IsValid(v9, pidl);
      if ( !v10 )
        goto LABEL_31;
      StringCchCopyW(v42, 0x104u, (const unsigned __int16 *)v10 + *(unsigned int *)((char *)v10 + 38) + 27);
      CDeviceCache::s_AddToStorageCache(v41, pidl, v42);
      if ( v31 )
      {
        if ( (*((_BYTE *)this + 12) & 0x20) == 0 )
        {
LABEL_31:
          if ( pidl )
          {
            ILFree(pidl);
            pidl = 0;
          }
          goto LABEL_36;
        }
      }
      else if ( (*((_BYTE *)this + 12) & 0x40) == 0 )
      {
        goto LABEL_31;
      }
      if ( (unsigned int)IsolationAwareDPA_InsertPtr(*v2, v11, pidl) != -1 )
        goto LABEL_36;
      goto LABEL_31;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))WPP_SF_S)(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        17,
        WPP_6ba37b08510337949ff0d977e37e44c8_Traceguids,
        (LARGE_INTEGER)pvar.hVal.QuadPart);
LABEL_36:
    PropVariantClear(&pvar);
    ++v8;
  }
  FileTime1 = FileTime;
  EnterCriticalSection(&g_csDeviceCache);
  if ( g_pDeviceCache )
  {
    Item = CDeviceCache::_FindItem(v12, v41);
    if ( Item )
    {
      v13 = 0;
      for ( i = 0; ; ++i )
      {
        v20 = (_DWORD *)*((_QWORD *)Item + 4);
        v21 = v20 ? *v20 : 0;
        if ( i >= v21 )
          break;
        Ptr = (const FILETIME *)IsolationAwareDPA_GetPtr(v20, i);
        v23 = Ptr;
        v37 = Ptr;
        if ( Ptr && CompareFileTime(&FileTime1, Ptr) > 0 )
        {
          for ( j = 0; ; ++j )
          {
            v25 = (CDeviceCache *)*((_QWORD *)Item + 3);
            v26 = v25 ? *(_DWORD *)v25 : 0;
            if ( j >= v26 )
              break;
            v27 = (const ITEMIDLIST *)IsolationAwareDPA_GetPtr(v25, j);
            if ( v27 )
            {
              v36 = 0;
              if ( (int)SHILCombine(v27, *(const ITEMIDLIST **)&v23[1], &v36) >= 0 )
              {
                v28 = v36;
                ChangeNotify(128, 0x3000u, v36, 0);
                if ( v28 )
                  ILFree(v28);
                v23 = v37;
              }
            }
          }
          if ( (unsigned int)CDeviceCache::_DeleteStorage(v25, Item, i) )
            --i;
        }
      }
    }
    else
    {
      v13 = -2147467259;
    }
  }
  else
  {
    v13 = 0;
  }
  LeaveCriticalSection(&g_csDeviceCache);
  if ( v13 < 0 )
  {
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v15 = 30;
      v16 = (unsigned int)v13;
      v17 = WPP_97b3e7d056e530596454d4c68ce08f99_Traceguids;
      goto LABEL_75;
    }
  }
LABEL_76:
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v33);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v34);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v32);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180064fa0  push    rbp
0x180064fa2  push    rbx
0x180064fa3  push    rsi
0x180064fa4  push    rdi
0x180064fa5  push    r12
0x180064fa7  push    r13
0x180064fa9  push    r14
0x180064fab  push    r15
0x180064fad  lea     rbp, [rsp-3D8h]
0x180064fb5  sub     rsp, 4D8h
0x180064fbc  mov     rax, cs:__security_cookie
0x180064fc3  xor     rax, rsp
0x180064fc6  mov     [rbp+410h+var_50], rax
0x180064fcd  mov     rsi, rcx
0x180064fd0  xor     r12d, r12d
0x180064fd3  mov     [rsp+510h+pidl], r12
0x180064fd8  mov     [rsp+510h+var_4D8], r12d
0x180064fdd  mov     qword ptr [rsp+510h+FileTime.dwLowDateTime], r12
0x180064fe2  xorps   xmm0, xmm0
0x180064fe5  movups  xmmword ptr [rbp+410h+SystemTime.wYear], xmm0
0x180064fe9  mov     [rsp+510h+var_4D0], r12
0x180064fee  mov     [rsp+510h+var_4C0], r12
0x180064ff3  mov     [rsp+510h+var_4C8], r12
0x180064ff8  lea     r14, [rcx+20h]
0x180064ffc  cmp     [r14], r12
0x180064fff  jz      short loc_180065009
0x180065001  mov     ebx, r12d
0x180065004  jmp     loc_180065463
0x180065009  xor     eax, eax
0x18006500b  movups  xmmword ptr [rsp+510h+pvar], xmm0
0x180065010  mov     qword ptr [rbp+410h+pvar+10h], rax
0x180065014  mov     rcx, r14
0x180065017  call    ?Create@?$CDPA_Base@UPROPERTY_ITEM@@@@QEAAHH@Z; CDPA_Base<PROPERTY_ITEM>::Create(int)
0x18006501c  mov     r15b, 2
0x18006501f  lea     r13, WPP_6ba37b08510337949ff0d977e37e44c8_Traceguids
0x180065026  test    eax, eax
0x180065028  jz      loc_1800653F3
0x18006502e  mov     rcx, [rsi+10h]
0x180065032  mov     rax, [rcx]
0x180065035  mov     r8d, 104h
0x18006503b  lea     rdx, [rbp+410h+var_470]
0x18006503f  mov     rax, [rax+60h]
0x180065043  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065048  mov     ebx, eax
0x18006504a  test    eax, eax
0x18006504c  jns     short loc_18006507C
0x18006504e  lea     rdi, WPP_GLOBAL_Control
0x180065055  mov     rcx, cs:WPP_GLOBAL_Control
0x18006505c  cmp     rcx, rdi
0x18006505f  jz      loc_180065425
0x180065065  test    [rcx+1Ch], r15b
0x180065069  jz      loc_180065425
0x18006506f  mov     edx, 0Dh
0x180065074  mov     r9d, eax
0x180065077  jmp     loc_180065419
0x18006507c  mov     rcx, [rsi+10h]
0x180065080  mov     rax, [rcx]
0x180065083  lea     r8, [rsp+510h+var_4D0]
0x180065088  mov     rdx, [rcx+40h]
0x18006508c  mov     rax, [rax+88h]
0x180065093  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065098  mov     ebx, eax
0x18006509a  test    eax, eax
0x18006509c  jns     short loc_1800650C6
0x18006509e  lea     rdi, WPP_GLOBAL_Control
0x1800650a5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800650ac  cmp     rcx, rdi
0x1800650af  jz      loc_180065425
0x1800650b5  test    [rcx+1Ch], r15b
0x1800650b9  jz      loc_180065425
0x1800650bf  mov     edx, 0Eh
0x1800650c4  jmp     short loc_180065074
0x1800650c6  mov     rcx, [rsp+510h+var_4D0]
0x1800650cb  mov     rax, [rcx]
0x1800650ce  lea     rdx, [rsp+510h+var_4C0]
0x1800650d3  mov     rax, [rax+30h]
0x1800650d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800650dc  mov     ebx, eax
0x1800650de  test    eax, eax
0x1800650e0  jns     short loc_18006510D
0x1800650e2  lea     rdi, WPP_GLOBAL_Control
0x1800650e9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800650f0  cmp     rcx, rdi
0x1800650f3  jz      loc_180065425
0x1800650f9  test    [rcx+1Ch], r15b
0x1800650fd  jz      loc_180065425
0x180065103  mov     edx, 0Fh
0x180065108  jmp     loc_180065074
0x18006510d  mov     rcx, [rsp+510h+var_4C0]
0x180065112  mov     rax, [rcx]
0x180065115  lea     r8, [rsp+510h+var_4C8]
0x18006511a  lea     rdx, WPD_FUNCTIONAL_CATEGORY_STORAGE
0x180065121  mov     rax, [rax+30h]
0x180065125  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006512a  mov     ebx, eax
0x18006512c  test    eax, eax
0x18006512e  jns     short loc_18006515B
0x180065130  lea     rdi, WPP_GLOBAL_Control
0x180065137  mov     rcx, cs:WPP_GLOBAL_Control
0x18006513e  cmp     rcx, rdi
0x180065141  jz      loc_180065425
0x180065147  test    [rcx+1Ch], r15b
0x18006514b  jz      loc_180065425
0x180065151  mov     edx, 10h
0x180065156  jmp     loc_180065074
0x18006515b  mov     r15d, r12d
0x18006515e  lea     rcx, [rbp+410h+SystemTime]; lpSystemTime
0x180065162  call    cs:__imp_GetSystemTime
0x180065168  lea     rdx, [rsp+510h+FileTime]; lpFileTime
0x18006516d  lea     rcx, [rbp+410h+SystemTime]; lpSystemTime
0x180065171  call    cs:__imp_SystemTimeToFileTime
0x180065177  lea     rdi, WPP_GLOBAL_Control
0x18006517e  mov     rcx, [rsp+510h+var_4C8]
0x180065183  mov     rax, [rcx]
0x180065186  lea     r8, [rsp+510h+pvar]
0x18006518b  mov     edx, r15d
0x18006518e  mov     rax, [rax+20h]
0x180065192  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065197  test    eax, eax
0x180065199  jnz     loc_18006529B
0x18006519f  mov     eax, 1Fh
0x1800651a4  cmp     ax, word ptr [rsp+510h+pvar]
0x1800651a9  jnz     loc_18006528E
0x1800651af  lea     rax, [rsp+510h+var_4D8]
0x1800651b4  mov     [rsp+510h+var_4F0], rax; int *
0x1800651b9  lea     r9, [rsp+510h+pidl]; struct _ITEMIDLIST **
0x1800651be  mov     r8, qword ptr [rsp+510h+pvar+8]; unsigned __int16 *
0x1800651c3  mov     rdx, [rsp+510h+var_4D0]; struct IPortableDevice *
0x1800651c8  mov     rcx, [rsi+10h]; this
0x1800651cc  call    ?_CreateIDList@CStorageFolder@@AEAAJPEAUIPortableDevice@@PEBGPEAPEFAU_ITEMIDLIST@@PEAH@Z; CStorageFolder::_CreateIDList(IPortableDevice *,ushort const *,_ITEMIDLIST * *,int *)
0x1800651d1  test    eax, eax
0x1800651d3  js      short loc_180065253
0x1800651d5  mov     rdx, [rsp+510h+pidl]; struct _ITEMIDLIST *
0x1800651da  call    ?_IsValid@CStorageFolder@@AEAAPEFBUSTORAGEITEM@@PEFBU_ITEMIDLIST@@@Z; CStorageFolder::_IsValid(_ITEMIDLIST const *)
0x1800651df  test    rax, rax
0x1800651e2  jz      short loc_18006523C
0x1800651e4  mov     ecx, [rax+26h]
0x1800651e7  add     rcx, 1Bh
0x1800651eb  lea     r8, [rax+rcx*2]; unsigned __int16 *
0x1800651ef  mov     edx, 104h; unsigned __int64
0x1800651f4  lea     rcx, [rbp+410h+var_260]; unsigned __int16 *
0x1800651fb  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180065200  lea     r8, [rbp+410h+var_260]; unsigned __int16 *
0x180065207  mov     rdx, [rsp+510h+pidl]; struct _ITEMIDLIST *
0x18006520c  lea     rcx, [rbp+410h+var_470]; unsigned __int16 *
0x180065210  call    ?s_AddToStorageCache@CDeviceCache@@CAJPEBGPEFAU_ITEMIDLIST@@0@Z; CDeviceCache::s_AddToStorageCache(ushort const *,_ITEMIDLIST *,ushort const *)
0x180065215  cmp     [rsp+510h+var_4D8], r12d
0x18006521a  jz      short loc_180065224
0x18006521c  test    byte ptr [rsi+0Ch], 20h
0x180065220  jnz     short loc_18006522A
0x180065222  jmp     short loc_18006523C
0x180065224  test    byte ptr [rsi+0Ch], 40h
0x180065228  jz      short loc_18006523C
0x18006522a  mov     r8, [rsp+510h+pidl]
0x18006522f  mov     rcx, [r14]
0x180065232  call    IsolationAwareDPA_InsertPtr
0x180065237  cmp     eax, 0FFFFFFFFh
0x18006523a  jnz     short loc_18006527B
0x18006523c  mov     rcx, [rsp+510h+pidl]; pidl
0x180065241  test    rcx, rcx
0x180065244  jz      short loc_18006527B
0x180065246  call    cs:__imp_ILFree
0x18006524c  mov     [rsp+510h+pidl], r12
0x180065251  jmp     short loc_18006527B
0x180065253  mov     rcx, cs:WPP_GLOBAL_Control
0x18006525a  cmp     rcx, rdi
0x18006525d  jz      short loc_18006527B
0x18006525f  test    byte ptr [rcx+1Ch], 40h
0x180065263  jz      short loc_18006527B
0x180065265  mov     edx, 11h
0x18006526a  mov     r9, qword ptr [rsp+510h+pvar+8]
0x18006526f  mov     r8, r13
0x180065272  mov     rcx, [rcx+10h]
0x180065276  call    WPP_SF_S
0x18006527b  lea     rcx, [rsp+510h+pvar]; pvar
0x180065280  call    cs:__imp_PropVariantClear
0x180065286  inc     r15d
0x180065289  jmp     loc_18006517E
0x18006528e  mov     ebx, 8000FFFFh
0x180065293  mov     r15b, 2
0x180065296  jmp     loc_180065425
0x18006529b  mov     rax, qword ptr [rsp+510h+FileTime.dwLowDateTime]
0x1800652a0  mov     qword ptr [rbp+410h+FileTime1.dwLowDateTime], rax
0x1800652a4  lea     rcx, ?g_csDeviceCache@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800652ab  call    cs:__imp_EnterCriticalSection
0x1800652b1  cmp     cs:?g_pDeviceCache@@3PEAVCDeviceCache@@EA, r12; CDeviceCache * g_pDeviceCache
0x1800652b8  jnz     short loc_180065301
0x1800652ba  mov     r14d, r12d
0x1800652bd  lea     rcx, ?g_csDeviceCache@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800652c4  call    cs:__imp_LeaveCriticalSection
0x1800652ca  test    r14d, r14d
0x1800652cd  jns     loc_180065463
0x1800652d3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800652da  cmp     rcx, rdi
0x1800652dd  jz      loc_180065463
0x1800652e3  test    byte ptr [rcx+1Ch], 2
0x1800652e7  jz      loc_180065463
0x1800652ed  mov     edx, 1Eh
0x1800652f2  mov     r9d, r14d
0x1800652f5  lea     r8, WPP_97b3e7d056e530596454d4c68ce08f99_Traceguids
0x1800652fc  jmp     loc_180065459
0x180065301  lea     rdx, [rbp+410h+var_470]; unsigned __int16 *
0x180065305  call    ?_FindItem@CDeviceCache@@AEAAPEAUDEVITEM_CACHE@@PEBG@Z; CDeviceCache::_FindItem(ushort const *)
0x18006530a  mov     r13, rax
0x18006530d  test    rax, rax
0x180065310  jnz     short loc_18006531A
0x180065312  mov     r14d, 80004005h
0x180065318  jmp     short loc_1800652BD
0x18006531a  mov     r14d, r12d
0x18006531d  mov     esi, r12d
0x180065320  mov     rcx, [r13+20h]
0x180065324  test    rcx, rcx
0x180065327  jz      short loc_18006532D
0x180065329  mov     eax, [rcx]
0x18006532b  jmp     short loc_180065330
0x18006532d  mov     eax, r12d
0x180065330  cmp     esi, eax
0x180065332  jge     short loc_1800652BD
0x180065334  movsxd  rdx, esi
0x180065337  call    IsolationAwareDPA_GetPtr
0x18006533c  mov     r12, rax
0x18006533f  mov     [rsp+510h+var_4A8], rax
0x180065344  test    rax, rax
0x180065347  jz      loc_1800653E9
0x18006534d  mov     rdx, rax; lpFileTime2
0x180065350  lea     rcx, [rbp+410h+FileTime1]; lpFileTime1
0x180065354  call    cs:__imp_CompareFileTime
0x18006535a  test    eax, eax
0x18006535c  jle     loc_1800653E9
0x180065362  xor     r15d, r15d
0x180065365  mov     rcx, [r13+18h]; this
0x180065369  test    rcx, rcx
0x18006536c  jz      short loc_180065372
0x18006536e  mov     eax, [rcx]
0x180065370  jmp     short loc_180065374
0x180065372  xor     eax, eax
0x180065374  cmp     r15d, eax
0x180065377  jge     short loc_1800653D3
0x180065379  movsxd  rdx, r15d
0x18006537c  call    IsolationAwareDPA_GetPtr
0x180065381  test    rax, rax
0x180065384  jz      short loc_1800653CE
0x180065386  mov     [rsp+510h+var_4B0], r14
0x18006538b  lea     r8, [rsp+510h+var_4B0]
0x180065390  mov     rdx, [r12+8]
0x180065395  mov     rcx, rax
0x180065398  call    SHILCombine
0x18006539d  test    eax, eax
0x18006539f  js      short loc_1800653CE
0x1800653a1  xor     r9d, r9d; dwItem2
0x1800653a4  mov     r12, [rsp+510h+var_4B0]
0x1800653a9  mov     r8, r12; dwItem1
0x1800653ac  mov     edx, 3000h; uFlags
0x1800653b1  mov     ecx, 80h; wEventId
0x1800653b6  call    ?ChangeNotify@@YAXJIPEFBU_ITEMIDLIST@@0@Z; ChangeNotify(long,uint,_ITEMIDLIST const *,_ITEMIDLIST const *)
0x1800653bb  test    r12, r12
0x1800653be  jz      short loc_1800653C9
0x1800653c0  mov     rcx, r12; pidl
0x1800653c3  call    cs:__imp_ILFree
0x1800653c9  mov     r12, [rsp+510h+var_4A8]
0x1800653ce  inc     r15d
0x1800653d1  jmp     short loc_180065365
0x1800653d3  mov     r8d, esi; int
0x1800653d6  mov     rdx, r13; struct DEVITEM_CACHE *
0x1800653d9  call    ?_DeleteStorage@CDeviceCache@@AEAAHPEAUDEVITEM_CACHE@@H@Z; CDeviceCache::_DeleteStorage(DEVITEM_CACHE *,int)
0x1800653de  xor     r12d, r12d
0x1800653e1  test    eax, eax
0x1800653e3  jz      short loc_1800653EC
0x1800653e5  dec     esi
0x1800653e7  jmp     short loc_1800653EC
0x1800653e9  xor     r12d, r12d
0x1800653ec  inc     esi
0x1800653ee  jmp     loc_180065320
0x1800653f3  mov     ebx, 8007000Eh
0x1800653f8  lea     rdi, WPP_GLOBAL_Control
0x1800653ff  mov     rcx, cs:WPP_GLOBAL_Control
0x180065406  cmp     rcx, rdi
0x180065409  jz      short loc_180065425
0x18006540b  test    [rcx+1Ch], r15b
0x18006540f  jz      short loc_180065425
0x180065411  mov     edx, 0Ch
0x180065416  mov     r9d, ebx
0x180065419  mov     r8, r13
0x18006541c  mov     rcx, [rcx+10h]
0x180065420  call    WPP_SF_d
0x180065425  mov     rcx, r14
0x180065428  call    ?DestroyCallback@?$CDPA@$$CFAU_ITEMIDLIST@@@@QEAAXP6AHPEFAU_ITEMIDLIST@@PEAX@Z1@Z; CDPA<_ITEMIDLIST>::DestroyCallback(int (*)(_ITEMIDLIST *,void *),void *)
0x18006542d  lea     rcx, [rsp+510h+pvar]; pvar
0x180065432  call    cs:__imp_PropVariantClear
0x180065438  test    ebx, ebx
0x18006543a  jns     short loc_180065463
0x18006543c  mov     rcx, cs:WPP_GLOBAL_Control
0x180065443  cmp     rcx, rdi
0x180065446  jz      short loc_180065463
0x180065448  test    [rcx+1Ch], r15b
0x18006544c  jz      short loc_180065463
0x18006544e  mov     edx, 12h
0x180065453  mov     r9d, ebx
0x180065456  mov     r8, r13
0x180065459  mov     rcx, [rcx+10h]
  ... truncated ...
```
