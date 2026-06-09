# CDVRFileCollection::RegisterReader(CDVRFileCollection::CClientInfo *,void (*)(void *,ulong,__int64,__int64),void *)

- ea: `0x1800754a4`
- end: `0x180075ac2`
- name: `?RegisterReader@CDVRFileCollection@@QEAAJPEAUCClientInfo@1@P6AXPEAXK_J2@Z1@Z`
- size: `1566`
- prototype: `__int64 __fastcall(CDVRFileCollection *__hidden this, struct CDVRFileCollection::CClientInfo *, void (*)(void *, unsigned int, __int64, __int64), void *)`
- caller_count: `2`
- callee_count: `15`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180063224`
- `0x180063528`

## callees

- `0x1800017a0`
- `0x180001c00`
- `0x18000262c`
- `0x180071cb0`
- `0x180071ffc`
- `0x180073368`
- `0x1800739f8`
- `0x180073ebc`
- `0x180074ec4`
- `0x180075408`
- `0x1800754a4`
- `0x180076810`
- `0x180076948`
- `0x1800769e8`
- `0x180085ef0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180075788`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x1800757a9`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180075788`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x1800757a9`
- `KERNEL32!CreateEventW` at `0x18007580e`
- `KERNEL32!CreateEventW` at `0x18007580e`
- `KERNEL32!CloseHandle` at `0x180075831`
- `KERNEL32!CloseHandle` at `0x180075a21`
- `KERNEL32!CloseHandle` at `0x180075a60`
- `KERNEL32!CloseHandle` at `0x1800b561d`
- `KERNEL32!CloseHandle` at `0x1800b566d`
- `KERNEL32!CloseHandle` at `0x180075831`
- `KERNEL32!CloseHandle` at `0x180075a21`
- `KERNEL32!CloseHandle` at `0x180075a60`
- `KERNEL32!CloseHandle` at `0x1800b561d`
- `KERNEL32!CloseHandle` at `0x1800b566d`
- `KERNEL32!GetLastError` at `0x18007581c`
- `KERNEL32!GetLastError` at `0x180075990`
- `KERNEL32!GetLastError` at `0x18007581c`
- `KERNEL32!GetLastError` at `0x180075990`
- `KERNEL32!RegisterWaitForSingleObject` at `0x180075986`
- `KERNEL32!RegisterWaitForSingleObject` at `0x180075986`

## pseudocode

```c
__int64 __fastcall CDVRFileCollection::RegisterReader(
        CDVRFileCollection *this,
        struct CDVRFileCollection::CClientInfo *a2,
        void (*a3)(void *, unsigned int, __int64, __int64),
        void *a4)
{
  __int64 v7; // r15
  unsigned int v8; // esi
  int v9; // r12d
  HANDLE EventW; // r14
  __int64 v11; // rdx
  int v12; // ebx
  enum _ACCESS_MODE v13; // r8d
  int i; // ecx
  bool v15; // zf
  signed int j; // r14d
  __int64 v17; // r12
  __int64 v18; // rcx
  int v19; // eax
  __int64 v20; // r12
  ULONG v21; // ecx
  int v22; // eax
  __int64 v23; // r9
  size_t v24; // rax
  wchar_t *p_Buffer; // rcx
  unsigned int k; // ebx
  struct _SECURITY_ATTRIBUTES *v27; // rcx
  DWORD LastError; // eax
  __int64 v29; // rax
  __int64 v30; // r12
  __int64 v31; // rax
  CDVRFileCollection::NotificationContext *v32; // rax
  void (*v33)(void *, unsigned int, __int64, __int64); // r9
  void *v34; // r14
  signed int v35; // eax
  enum _ACCESS_MODE dwMilliseconds; // [rsp+20h] [rbp-158h]
  HANDLE v37; // [rsp+48h] [rbp-130h]
  int v38; // [rsp+58h] [rbp-120h] BYREF
  int v39; // [rsp+5Ch] [rbp-11Ch]
  unsigned int v40; // [rsp+60h] [rbp-118h] BYREF
  size_t v41; // [rsp+68h] [rbp-110h] BYREF
  unsigned int v42; // [rsp+70h] [rbp-108h]
  HANDLE hObject[2]; // [rsp+78h] [rbp-100h] BYREF
  void *v44; // [rsp+88h] [rbp-F0h] BYREF
  UUID v45; // [rsp+90h] [rbp-E8h] BYREF
  __int64 v46; // [rsp+A0h] [rbp-D8h]
  void *v47; // [rsp+A8h] [rbp-D0h]
  struct CDVRFileCollection::CClientInfo *v48; // [rsp+B0h] [rbp-C8h]
  struct _ACL *v49; // [rsp+B8h] [rbp-C0h] BYREF
  HANDLE phNewWaitObject; // [rsp+C0h] [rbp-B8h] BYREF
  __int128 v51; // [rsp+C8h] [rbp-B0h] BYREF
  __int64 v52; // [rsp+D8h] [rbp-A0h]
  WCHAR Name[22]; // [rsp+E0h] [rbp-98h] BYREF
  char v54; // [rsp+10Ch] [rbp-6Ch] BYREF
  wchar_t Buffer; // [rsp+10Eh] [rbp-6Ah] BYREF

  v47 = a4;
  hObject[1] = this;
  v48 = a2;
  if ( !a2 )
    return 2147942487LL;
  v7 = 0;
  v46 = 0;
  v40 = 0;
  v8 = -1;
  v9 = 0;
  EventW = 0;
  v37 = 0;
  v39 = 0;
  hObject[0] = 0;
  v12 = CDVRFileCollection::Lock((__int64)this, a2, &v40, 0x18u, 0);
  v38 = v12;
  if ( v12 < 0 )
    goto LABEL_59;
  v11 = *((_QWORD *)this + 4);
  if ( !*(_DWORD *)(v11 + 60) || (*((_BYTE *)this + 172) & 8) != 0 )
  {
    v8 = 32;
    v12 = 0;
    goto LABEL_59;
  }
  for ( i = 0; ; ++i )
  {
    v15 = i == 32;
    if ( i >= 32 )
      break;
    v13 = 5 * i;
    if ( (*(_BYTE *)(v11 + 40LL * i + 654) & 1) == 0 )
    {
      *(_QWORD *)(v11 + 40LL * i + 616) = 0;
      *(_DWORD *)(*((_QWORD *)this + 4) + 40LL * i + 624) = 0;
      v8 = i;
      v15 = i == 32;
      break;
    }
  }
  if ( v15 )
  {
    v12 = -2147024882;
    for ( j = 0; ; ++j )
    {
      v17 = 40LL * j;
      if ( j >= 32 )
        break;
      v18 = *((_QWORD *)this + 4);
      LODWORD(v41) = 0;
      v19 = ReaderEventExists(v17 + v18 + 628, &v41);
      v11 = (unsigned int)v41;
      if ( v19 < 0 )
        v11 = 0;
      LODWORD(v41) = v11;
      if ( !(_DWORD)v11 )
      {
        v12 = CDVRFileCollection::UnregisterReader(this, a2, j);
        break;
      }
    }
    if ( v12 < 0 )
      goto LABEL_23;
    *(_DWORD *)(*((_QWORD *)this + 4) + v17 + 624) = 0;
    *(_WORD *)(*((_QWORD *)this + 4) + v17 + 654) = 0;
    *(_WORD *)(*((_QWORD *)this + 4) + v17 + 652) = 0;
    v8 = j;
    EventW = 0;
  }
  v20 = 5LL * v8;
  *(_WORD *)(*((_QWORD *)this + 4) + 8 * v20 + 652) = 0;
  *(_WORD *)(*((_QWORD *)this + 4) + 8 * v20 + 654) = 7;
  _InterlockedIncrement((volatile signed __int32 *)(*((_QWORD *)this + 4) + 56LL));
  v39 = 1;
  v49 = 0;
  v44 = 0;
  v51 = 0;
  v52 = 0;
  v21 = *((_DWORD *)a2 + 4);
  if ( !v21 )
  {
LABEL_27:
    if ( (unsigned int)GetProcessIntegrityLevel() == 4096 )
    {
      _o_wcscpy_s(Name, 39, L"Local\\_MS_TSDVR_EVENT_", v23);
      v24 = 18;
      p_Buffer = (wchar_t *)&v54;
    }
    else
    {
      _o_wcscpy_s(Name, 40, L"Global\\_MS_TSDVR_EVENT_", v23);
      v24 = 17;
      p_Buffer = &Buffer;
    }
    *(_QWORD *)&v45.Data1 = p_Buffer;
    v41 = v24;
    v42 = 0;
    for ( k = 1; ; ++k )
    {
      v42 = k;
      if ( k == -1 )
        break;
      swprintf_s(p_Buffer, v24, L"%u", k);
      v27 = (struct _SECURITY_ATTRIBUTES *)&v51;
      if ( !*((_DWORD *)a2 + 4) )
        v27 = 0;
      EventW = CreateEventW(v27, 0, 0, Name);
      v37 = EventW;
      LastError = GetLastError();
      if ( EventW )
      {
        if ( LastError != 183 )
          break;
        CloseHandle(EventW);
        EventW = 0;
        v37 = 0;
      }
      v24 = v41;
      p_Buffer = *(wchar_t **)&v45.Data1;
    }
    if ( *((_DWORD *)a2 + 4) )
      FreeSecurityDescriptors(&v49, &v44);
    if ( EventW )
    {
      v29 = *((_QWORD *)this + 4);
      if ( *(_DWORD *)(v29 + 68) )
        *(_DWORD *)(v29 + 40LL * v8 + 624) = k;
      v30 = *((_QWORD *)this + 4);
      v45 = 0;
      v12 = CreateReaderIdEvent(*((_DWORD *)a2 + 4), *((void ***)a2 + 3), &v45, hObject);
      if ( v12 >= 0 )
      {
        v31 = 5LL * v8;
        *(UUID *)(v30 + 8 * v31 + 628) = v45;
        ++*(_DWORD *)(v30 + 8 * v31 + 644);
      }
      v38 = v12;
      if ( v12 >= 0 )
      {
        v32 = (CDVRFileCollection::NotificationContext *)operator new(0x48u);
        if ( v32 )
        {
          v7 = CDVRFileCollection::NotificationContext::NotificationContext(v32, this, EventW, v33, v47, a2, v8, &v38);
          v12 = v38;
        }
        else
        {
          v7 = 0;
        }
        v46 = v7;
        if ( v7 )
        {
          if ( v12 >= 0 )
          {
            v34 = 0;
            phNewWaitObject = 0;
            if ( RegisterWaitForSingleObject(
                   &phNewWaitObject,
                   *(HANDLE *)(v7 + 40),
                   CDVRFileCollection::RegisterWaitCallback,
                   (PVOID)v7,
                   0xFFFFFFFF,
                   0x10u) )
            {
              *(_QWORD *)(v7 + 48) = phNewWaitObject;
              *((_QWORD *)this + v8 + 22) = v7;
              v9 = 1;
              v12 = 0;
            }
            else
            {
              v35 = GetLastError();
              v12 = v35;
              if ( v35 > 0 )
                v12 = (unsigned __int16)v35 | 0x80070000;
              v9 = 0;
            }
            goto LABEL_60;
          }
        }
        else
        {
          v12 = -2147024882;
        }
      }
    }
    else
    {
      v12 = -2147467259;
    }
    goto LABEL_23;
  }
  v22 = CreateACL(v21, *((void ***)a2 + 3), v13, 2031619, dwMilliseconds, 2u, &v49, &v44);
  v12 = v22;
  if ( !v22 )
  {
    LODWORD(v51) = 24;
    *((_QWORD *)&v51 + 1) = v44;
    LODWORD(v52) = 0;
    goto LABEL_27;
  }
  if ( v22 > 0 )
    v12 = (unsigned __int16)v22 | 0x80070000;
LABEL_23:
  v9 = 0;
LABEL_59:
  v34 = v37;
LABEL_60:
  if ( v12 >= 0 )
  {
    CDVRFileCollection::CClientInfo::SetReaderIndex(a2, v8, hObject[0]);
  }
  else
  {
    if ( v8 != -1 )
    {
      v11 = 5LL * v8;
      *(_WORD *)(*((_QWORD *)this + 4) + 8 * v11 + 654) = 0;
      *(_DWORD *)(*((_QWORD *)this + 4) + 8 * v11 + 624) = 0;
    }
    if ( v34 )
      CloseHandle(v34);
    if ( v7 )
      CDVRFileCollection::NotificationContext::`scalar deleting destructor'(
        (CDVRFileCollection::NotificationContext *)v7,
        v11);
    if ( v9 )
      *((_QWORD *)this + v8 + 22) = 0;
    if ( v39 )
      _InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)this + 4) + 56LL));
    if ( hObject[0] )
      CloseHandle(hObject[0]);
  }
  CDVRFileCollection::Unlock(this, v11, v40, 24, 0);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x1800754a4  push    rbx
0x1800754a6  push    rsi
0x1800754a7  push    rdi
0x1800754a8  push    r12
0x1800754aa  push    r13
0x1800754ac  push    r14
0x1800754ae  push    r15
0x1800754b0  sub     rsp, 140h
0x1800754b7  mov     rax, cs:__security_cookie
0x1800754be  xor     rax, rsp
0x1800754c1  mov     [rsp+178h+var_48], rax
0x1800754c9  mov     [rsp+178h+var_D0], r9
0x1800754d1  mov     r13, rdx
0x1800754d4  mov     rdi, rcx
0x1800754d7  mov     [rsp+178h+var_F8], rcx
0x1800754df  mov     [rsp+178h+var_C8], rdx
0x1800754e7  xor     edx, edx
0x1800754e9  test    r13, r13
0x1800754ec  jnz     short loc_1800754F8
0x1800754ee  mov     eax, 80070057h
0x1800754f3  jmp     loc_180075A9F
0x1800754f8  mov     r15, rdx
0x1800754fb  mov     [rsp+178h+var_D8], rdx
0x180075503  mov     [rsp+178h+var_118], edx
0x180075507  or      esi, 0FFFFFFFFh
0x18007550a  mov     [rsp+178h+var_128], esi
0x18007550e  mov     r12d, edx
0x180075511  mov     [rsp+178h+var_134], edx
0x180075515  mov     r14, rdx
0x180075518  mov     [rsp+178h+var_130], rdx
0x18007551d  mov     [rsp+178h+var_11C], edx
0x180075521  mov     [rsp+178h+hObject], rdx
0x180075526  mov     [rsp+178h+var_138], 80004005h
0x18007552e  mov     [rsp+178h+dwMilliseconds], edx; enum _ACCESS_MODE
0x180075532  mov     r9d, 18h
0x180075538  lea     r8, [rsp+178h+var_118]
0x18007553d  mov     rdx, r13
0x180075540  call    ?Lock@CDVRFileCollection@@QEAAJPEBUCClientInfo@1@AEAHW4DVRFILECOLLECTIONCALLER@@H@Z; CDVRFileCollection::Lock(CDVRFileCollection::CClientInfo const *,int &,DVRFILECOLLECTIONCALLER,int)
0x180075545  mov     ebx, eax
0x180075547  mov     [rsp+178h+var_120], eax
0x18007554b  test    eax, eax
0x18007554d  jns     short loc_180075558
0x18007554f  mov     [rsp+178h+var_138], eax
0x180075553  jmp     loc_1800759E8
0x180075558  mov     rdx, [rdi+20h]
0x18007555c  cmp     dword ptr [rdx+3Ch], 0
0x180075560  jz      loc_1800759D9
0x180075566  test    byte ptr [rdi+0ACh], 8
0x18007556d  jnz     loc_1800759D9
0x180075573  xor     ecx, ecx
0x180075575  mov     [rsp+178h+var_124], ecx
0x180075579  cmp     ecx, 20h ; ' '
0x18007557c  jge     short loc_1800755B9
0x18007557e  movsxd  rax, ecx
0x180075581  lea     r8, [rax+rax*4]
0x180075585  test    byte ptr [rdx+r8*8+28Eh], 1
0x18007558e  jnz     loc_180075733
0x180075594  mov     qword ptr [rdx+r8*8+268h], 0
0x1800755a0  mov     rax, [rdi+20h]
0x1800755a4  mov     dword ptr [rax+r8*8+270h], 0
0x1800755b0  mov     esi, ecx
0x1800755b2  mov     [rsp+178h+var_128], ecx
0x1800755b6  cmp     ecx, 20h ; ' '
0x1800755b9  jnz     loc_180075673
0x1800755bf  mov     ebx, 8007000Eh
0x1800755c4  mov     [rsp+178h+var_138], ebx
0x1800755c8  xor     r14d, r14d
0x1800755cb  mov     [rsp+178h+var_124], r14d
0x1800755d0  movsxd  rax, r14d
0x1800755d3  lea     rcx, [rax+rax*4]
0x1800755d7  lea     r12, ds:0[rcx*8]
0x1800755df  cmp     r14d, 20h ; ' '
0x1800755e3  jge     short loc_180075632
0x1800755e5  mov     rcx, [rdi+20h]
0x1800755e9  mov     dword ptr [rsp+178h+var_110], 0
0x1800755f1  add     rcx, 274h
0x1800755f8  add     rcx, r12
0x1800755fb  lea     rdx, [rsp+178h+var_110]
0x180075600  call    ReaderEventExists
0x180075605  mov     ecx, eax
0x180075607  mov     edx, dword ptr [rsp+178h+var_110]
0x18007560b  xor     eax, eax
0x18007560d  test    ecx, ecx
0x18007560f  cmovs   edx, eax
0x180075612  mov     dword ptr [rsp+178h+var_110], edx
0x180075616  test    edx, edx
0x180075618  jnz     loc_18007573A
0x18007561e  mov     r8d, r14d; unsigned int
0x180075621  mov     rdx, r13; struct CDVRFileCollection::CClientInfo *
0x180075624  mov     rcx, rdi; this
0x180075627  call    ?UnregisterReader@CDVRFileCollection@@QEAAJPEBUCClientInfo@1@K@Z; CDVRFileCollection::UnregisterReader(CDVRFileCollection::CClientInfo const *,ulong)
0x18007562c  mov     ebx, eax
0x18007562e  mov     [rsp+178h+var_138], eax
0x180075632  test    ebx, ebx
0x180075634  js      loc_180075729
0x18007563a  mov     rax, [rdi+20h]
0x18007563e  mov     dword ptr [rax+r12+270h], 0
0x18007564a  mov     rcx, [rdi+20h]
0x18007564e  xor     eax, eax
0x180075650  mov     [rcx+r12+28Eh], ax
0x180075659  mov     rcx, [rdi+20h]
0x18007565d  mov     [rcx+r12+28Ch], ax
0x180075666  mov     esi, r14d
0x180075669  mov     [rsp+178h+var_128], r14d
0x18007566e  mov     r14, [rsp+178h+var_130]
0x180075673  mov     eax, esi
0x180075675  lea     r12, [rax+rax*4]
0x180075679  mov     rcx, [rdi+20h]
0x18007567d  xor     eax, eax
0x18007567f  mov     [rcx+r12*8+28Ch], ax
0x180075688  mov     rax, [rdi+20h]
0x18007568c  mov     ecx, 7
0x180075691  mov     [rax+r12*8+28Eh], cx
0x18007569a  mov     rax, [rdi+20h]
0x18007569e  lock inc dword ptr [rax+38h]
0x1800756a2  mov     [rsp+178h+var_11C], 1
0x1800756aa  mov     [rsp+178h+var_C0], 0
0x1800756b6  mov     [rsp+178h+var_F0], 0
0x1800756c2  xorps   xmm0, xmm0
0x1800756c5  xor     eax, eax
0x1800756c7  movups  [rsp+178h+var_B0], xmm0
0x1800756cf  mov     [rsp+178h+var_A0], rax
0x1800756d7  mov     ecx, [r13+10h]; cCountOfExplicitEntries
0x1800756db  test    ecx, ecx
0x1800756dd  jz      loc_180075768
0x1800756e3  lea     rax, [rsp+178h+var_F0]
0x1800756eb  mov     [rsp+178h+var_140], rax; void **
0x1800756f0  lea     rax, [rsp+178h+var_C0]
0x1800756f8  mov     [rsp+178h+var_148], rax; struct _ACL **
0x1800756fd  mov     [rsp+178h+dwFlags], 2; unsigned int
0x180075705  mov     r9d, 1F0003h; unsigned int
0x18007570b  mov     rdx, [r13+18h]; void **
0x18007570f  call    ?CreateACL@@YAKKPEAPEAXW4_ACCESS_MODE@@K1KAEAPEAU_ACL@@AEAPEAX@Z; CreateACL(ulong,void * *,_ACCESS_MODE,ulong,_ACCESS_MODE,ulong,_ACL * &,void * &)
0x180075714  mov     ebx, eax
0x180075716  test    eax, eax
0x180075718  jz      short loc_180075742
0x18007571a  jle     short loc_180075725
0x18007571c  movzx   ebx, ax
0x18007571f  or      ebx, 80070000h
0x180075725  mov     [rsp+178h+var_138], ebx
0x180075729  mov     r12d, [rsp+178h+var_134]
0x18007572e  jmp     loc_1800759E8
0x180075733  inc     ecx
0x180075735  jmp     loc_180075575
0x18007573a  inc     r14d
0x18007573d  jmp     loc_1800755CB
0x180075742  mov     dword ptr [rsp+178h+var_B0], 18h
0x18007574d  mov     rax, [rsp+178h+var_F0]
0x180075755  mov     qword ptr [rsp+178h+var_B0+8], rax
0x18007575d  mov     dword ptr [rsp+178h+var_A0], 0
0x180075768  call    ?GetProcessIntegrityLevel@@YAKXZ; GetProcessIntegrityLevel(void)
0x18007576d  lea     rcx, [rsp+178h+Name]
0x180075775  cmp     eax, 1000h
0x18007577a  jnz     short loc_18007579D
0x18007577c  lea     r8, aLocalMsTsdvrEv; "Local\\_MS_TSDVR_EVENT_"
0x180075783  mov     edx, 27h ; '''
0x180075788  call    cs:__imp__o_wcscpy_s
0x18007578e  mov     eax, 12h
0x180075793  lea     rcx, [rsp+178h+var_6C]
0x18007579b  jmp     short loc_1800757BC
0x18007579d  lea     r8, aGlobalMsTsdvrE; "Global\\_MS_TSDVR_EVENT_"
0x1800757a4  mov     edx, 28h ; '('
0x1800757a9  call    cs:__imp__o_wcscpy_s
0x1800757af  mov     eax, 11h
0x1800757b4  lea     rcx, [rsp+178h+Buffer]; Buffer
0x1800757bc  mov     qword ptr [rsp+178h+var_E8], rcx
0x1800757c4  mov     [rsp+178h+var_110], rax
0x1800757c9  mov     [rsp+178h+var_108], 0
0x1800757d1  mov     ebx, 1
0x1800757d6  mov     [rsp+178h+var_108], ebx
0x1800757da  cmp     ebx, 0FFFFFFFFh
0x1800757dd  jnb     short loc_180075850
0x1800757df  mov     r9d, ebx
0x1800757e2  lea     r8, aU; "%u"
0x1800757e9  mov     rdx, rax; BufferCount
0x1800757ec  call    swprintf_s
0x1800757f1  lea     rcx, [rsp+178h+var_B0]
0x1800757f9  xor     edx, edx; bManualReset
0x1800757fb  cmp     [r13+10h], edx
0x1800757ff  cmovbe  rcx, rdx; lpEventAttributes
0x180075803  lea     r9, [rsp+178h+Name]; lpName
0x18007580b  xor     r8d, r8d; bInitialState
0x18007580e  call    cs:__imp_CreateEventW
0x180075814  mov     r14, rax
0x180075817  mov     [rsp+178h+var_130], rax
0x18007581c  call    cs:__imp_GetLastError
0x180075822  test    r14, r14
0x180075825  jz      short loc_18007583F
0x180075827  cmp     eax, 0B7h
0x18007582c  jnz     short loc_180075850
0x18007582e  mov     rcx, r14; hObject
0x180075831  call    cs:__imp_CloseHandle
0x180075837  xor     r14d, r14d
0x18007583a  mov     [rsp+178h+var_130], r14
0x18007583f  inc     ebx
0x180075841  mov     rax, [rsp+178h+var_110]
0x180075846  mov     rcx, qword ptr [rsp+178h+var_E8]
0x18007584e  jmp     short loc_1800757D6
0x180075850  cmp     dword ptr [r13+10h], 0
0x180075855  jbe     short loc_18007586C
0x180075857  lea     rdx, [rsp+178h+var_F0]; void **
0x18007585f  lea     rcx, [rsp+178h+var_C0]; struct _ACL **
0x180075867  call    ?FreeSecurityDescriptors@@YAXAEAPEAU_ACL@@AEAPEAX@Z; FreeSecurityDescriptors(_ACL * &,void * &)
0x18007586c  test    r14, r14
0x18007586f  jnz     short loc_18007587B
0x180075871  mov     ebx, 80004005h
0x180075876  jmp     loc_180075725
0x18007587b  mov     rax, [rdi+20h]
0x18007587f  cmp     dword ptr [rax+44h], 0
0x180075883  jz      short loc_18007588D
0x180075885  mov     [rax+r12*8+270h], ebx
0x18007588d  mov     r12, [rdi+20h]
0x180075891  xorps   xmm0, xmm0
0x180075894  movups  [rsp+178h+var_E8], xmm0
0x18007589c  lea     r9, [rsp+178h+hObject]
0x1800758a1  lea     r8, [rsp+178h+var_E8]
0x1800758a9  mov     rdx, [r13+18h]; void **
0x1800758ad  mov     ecx, [r13+10h]; cCountOfExplicitEntries
0x1800758b1  call    CreateReaderIdEvent
0x1800758b6  mov     ebx, eax
0x1800758b8  test    eax, eax
0x1800758ba  js      short loc_1800758DC
0x1800758bc  movups  xmm0, [rsp+178h+var_E8]
0x1800758c4  mov     ecx, esi
0x1800758c6  lea     rax, [rcx+rcx*4]
0x1800758ca  movdqu  xmmword ptr [r12+rax*8+274h], xmm0
0x1800758d4  inc     dword ptr [r12+rax*8+284h]
0x1800758dc  mov     [rsp+178h+var_120], ebx
0x1800758e0  test    ebx, ebx
0x1800758e2  js      loc_180075725
0x1800758e8  mov     ecx, 48h ; 'H'; Size
0x1800758ed  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800758f2  test    rax, rax
0x1800758f5  jz      short loc_18007592E
0x1800758f7  lea     rcx, [rsp+178h+var_120]
0x1800758fc  mov     [rsp+178h+var_140], rcx; int *
0x180075901  mov     dword ptr [rsp+178h+var_148], esi; unsigned int
0x180075905  mov     qword ptr [rsp+178h+dwFlags], r13; struct CDVRFileCollection::CClientInfo *
0x18007590a  mov     rcx, [rsp+178h+var_D0]
0x180075912  mov     qword ptr [rsp+178h+dwMilliseconds], rcx; void *
0x180075917  mov     r8, r14; void *
0x18007591a  mov     rdx, rdi; struct CDVRFileCollection *
0x18007591d  mov     rcx, rax; this
0x180075920  call    ??0NotificationContext@CDVRFileCollection@@QEAA@PEAV1@PEAXP6AX1K_J2@Z1PEAUCClientInfo@1@KPEAJ@Z; CDVRFileCollection::NotificationContext::NotificationContext(CDVRFileCollection *,void *,void (*)(void *,ulong,__int64,__int64),void *,CDVRFileCollection::CClientInfo *,ulong,long *)
0x180075925  mov     r15, rax
0x180075928  mov     ebx, [rsp+178h+var_120]
0x18007592c  jmp     short loc_180075931
0x18007592e  xor     r15d, r15d
0x180075931  mov     [rsp+178h+var_D8], r15
0x180075939  test    r15, r15
0x18007593c  jnz     short loc_180075948
0x18007593e  mov     ebx, 8007000Eh
0x180075943  jmp     loc_180075725
0x180075948  test    ebx, ebx
0x18007594a  js      loc_180075725
0x180075950  xor     r14d, r14d
0x180075953  mov     [rsp+178h+var_130], r14
0x180075958  mov     [rsp+178h+phNewWaitObject], r14
0x180075960  mov     [rsp+178h+dwFlags], 10h; dwFlags
0x180075968  mov     [rsp+178h+dwMilliseconds], 0FFFFFFFFh; dwMilliseconds
0x180075970  mov     r9, r15; Context
0x180075973  lea     r8, ?RegisterWaitCallback@CDVRFileCollection@@KAXPEAXE@Z; Callback
0x18007597a  mov     rdx, [r15+28h]; hObject
0x18007597e  lea     rcx, [rsp+178h+phNewWaitObject]; phNewWaitObject
0x180075986  call    cs:__imp_RegisterWaitForSingleObject
0x18007598c  test    eax, eax
0x18007598e  jnz     short loc_1800759B0
0x180075990  call    cs:__imp_GetLastError
0x180075996  mov     ebx, eax
0x180075998  test    eax, eax
0x18007599a  jle     short loc_1800759A5
0x18007599c  movzx   ebx, ax
0x18007599f  or      ebx, 80070000h
0x1800759a5  mov     [rsp+178h+var_138], ebx
0x1800759a9  mov     r12d, [rsp+178h+var_134]
0x1800759ae  jmp     short loc_1800759ED
0x1800759b0  mov     rax, [rsp+178h+phNewWaitObject]
0x1800759b8  mov     [r15+30h], rax
0x1800759bc  mov     eax, esi
0x1800759be  mov     [rdi+rax*8+0B0h], r15
0x1800759c6  mov     r12d, 1
0x1800759cc  mov     [rsp+178h+var_134], r12d
0x1800759d1  xor     ebx, ebx
0x1800759d3  mov     [rsp+178h+var_138], ebx
0x1800759d7  jmp     short loc_1800759ED
0x1800759d9  mov     esi, 20h ; ' '
0x1800759de  mov     [rsp+178h+var_128], esi
0x1800759e2  xor     ebx, ebx
0x1800759e4  mov     [rsp+178h+var_138], ebx
0x1800759e8  mov     r14, [rsp+178h+var_130]
0x1800759ed  test    ebx, ebx
0x1800759ef  jns     short loc_180075A68
0x1800759f1  cmp     esi, 0FFFFFFFFh
0x1800759f4  jz      short loc_180075A19
0x1800759f6  mov     eax, esi
0x1800759f8  lea     rdx, [rax+rax*4]
0x1800759fc  mov     rcx, [rdi+20h]
0x180075a00  xor     eax, eax
0x180075a02  mov     [rcx+rdx*8+28Eh], ax
0x180075a0a  mov     rax, [rdi+20h]
  ... truncated ...
```
