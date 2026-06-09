# Storage::CVolume::GetIconAndLabelInfo(ushort *,ulong,ushort *,ulong,ushort *,ulong,ushort *,ulong,ushort *,ulong)

- ea: `0x180019280`
- end: `0x1800194c0`
- name: `?GetIconAndLabelInfo@CVolume@Storage@@QEAAJPEAGK0K0K0K0K@Z`
- size: `576`
- prototype: `int(Storage::CVolume *__hidden this, unsigned __int16 *, unsigned int, unsigned __int16 *, unsigned int, unsigned __int16 *, unsigned int, unsigned __int16 *, unsigned int, unsigned __int16 *, unsigned int)`
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180001ed0`
- `0x1800185c8`

## callees

- `0x180003570`
- `0x180004400`
- `0x180004de0`
- `0x180005e80`
- `0x180007b04`
- `0x180007b20`
- `0x1800140f0`
- `0x180014ae0`
- `0x180017854`
- `0x180019280`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800193bd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019408`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800193bd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019408`

## pseudocode

```c
__int64 __fastcall Storage::CVolume::GetIconAndLabelInfo(
        Storage::CVolume *this,
        unsigned __int16 *a2,
        __int64 a3,
        unsigned __int16 *a4,
        unsigned int a5,
        unsigned __int16 *a6,
        unsigned int a7,
        CRefCounted *a8,
        unsigned int a9,
        unsigned __int8 *a10)
{
  unsigned __int16 *v10; // rdi
  char *v11; // r12
  unsigned __int16 *v12; // r14
  unsigned __int8 *v13; // rsi
  struct Autoplay::IDeviceProperties **v17; // r9
  bool v18; // zf
  struct _WORD_BLOB **v19; // r9
  Settings *v20; // rbx
  struct _WORD_BLOB **v21; // r9
  void *v22; // r10
  void *v23; // r10
  int MultiDeviceGroupPropertyData; // eax
  unsigned __int8 *v26; // [rsp+20h] [rbp-58h]
  unsigned __int8 *v27; // [rsp+20h] [rbp-58h]
  unsigned __int8 *v28; // [rsp+20h] [rbp-58h]
  unsigned int v29; // [rsp+28h] [rbp-50h]
  unsigned int v30; // [rsp+28h] [rbp-50h]

  v10 = a6;
  v11 = (char *)this + 3216;
  v12 = (unsigned __int16 *)a8;
  v13 = a10;
  *a2 = 0;
  *a4 = 0;
  *v10 = 0;
  *v12 = 0;
  *(_WORD *)v13 = 0;
  CCritSectWithResource<CNamedElemList<PnPServices::CHandleNotif>>::Enter((char *)this + 3216);
  if ( (*((_BYTE *)this + 48) & 2) == 0 )
  {
    v18 = (*((_BYTE *)this + 44) & 1) == 0;
    a8 = 0;
    if ( !v18 )
    {
      if ( *((_WORD *)this + 168) && (int)StringCchCopyW(a2, 0x110u, (const unsigned __int16 *)this + 168) < 0 )
        *a2 = 0;
      if ( *((_WORD *)this + 440) && (int)StringCchCopyW(a4, 0x21u, (const unsigned __int16 *)this + 440) < 0 )
        *a4 = 0;
    }
    if ( *((_DWORD *)this + 801)
      && (int)PnPHelper::CreatePnPDevicePropertiesObject(
                (Storage::CVolume *)((char *)this + 2648),
                (struct PnPHelper::CHWDeviceInst *)(((unsigned __int64)this + 16)
                                                  & ((unsigned __int128)-(__int128)(unsigned __int64)this >> 64)),
                (struct CRefCounted *)&a8,
                v17) >= 0 )
    {
      v20 = a8;
      a6 = 0;
      if ( (int)Settings::GetDevicePropertyAsMultiSz(
                  a8,
                  (struct Autoplay::IDeviceProperties *)L"Icons",
                  (unsigned __int16 *)&a6,
                  v19) < 0 )
      {
        *v10 = 0;
      }
      else
      {
        if ( (int)StringCchCopyW(v10, 0x110u, a6 + 2) < 0 )
          *v10 = 0;
        CoTaskMemFree(v22);
      }
      if ( (int)Settings::GetDevicePropertyAsMultiSz(
                  v20,
                  (struct Autoplay::IDeviceProperties *)L"NoMediaIcons",
                  (unsigned __int16 *)&a6,
                  v21) < 0 )
      {
        *v12 = 0;
      }
      else
      {
        if ( (int)StringCchCopyW(v12, 0x110u, a6 + 2) < 0 )
          *v12 = 0;
        CoTaskMemFree(v23);
      }
      MultiDeviceGroupPropertyData = (*(__int64 (__fastcall **)(Settings *, const WCHAR *, unsigned __int8 *, __int64))(*(_QWORD *)v20 + 24LL))(
                                       v20,
                                       L"Label",
                                       v13,
                                       272);
      if ( MultiDeviceGroupPropertyData == -2147467259 )
      {
        LODWORD(v26) = 544;
        MultiDeviceGroupPropertyData = Settings::_GetMultiDeviceGroupPropertyData(
                                         v20,
                                         (struct Autoplay::IDeviceProperties *)L"Label",
                                         (const unsigned __int16 *)1,
                                         (unsigned int)v13,
                                         v26,
                                         v29);
        if ( MultiDeviceGroupPropertyData == -2147467259 )
        {
          LODWORD(v27) = 544;
          MultiDeviceGroupPropertyData = Settings::_GetDeviceGroupPropertyData(
                                           v20,
                                           (struct Autoplay::IDeviceProperties *)L"Label",
                                           (const unsigned __int16 *)1,
                                           (unsigned int)v13,
                                           v27,
                                           v30);
          if ( MultiDeviceGroupPropertyData == -2147467259 )
          {
            LODWORD(v28) = 544;
            MultiDeviceGroupPropertyData = Settings::_GetDeviceClassPropertyData(
                                             v20,
                                             (struct Autoplay::IDeviceProperties *)L"Label",
                                             (const unsigned __int16 *)1,
                                             v13,
                                             v28);
          }
        }
      }
      if ( MultiDeviceGroupPropertyData < 0 )
        *(_WORD *)v13 = 0;
      CRefCounted::Release(v20);
    }
  }
  CCritSectWithResource<CDummyResource>::Leave(v11);
  return 0;
}

```

## disassembly

```asm
0x180019280  push    rbx
0x180019282  push    rbp
0x180019283  push    rsi
0x180019284  push    rdi
0x180019285  push    r12
0x180019287  push    r13
0x180019289  push    r14
0x18001928b  push    r15
0x18001928d  sub     rsp, 38h
0x180019291  mov     rdi, [rsp+78h+arg_28]
0x180019299  lea     r12, [rcx+0C90h]
0x1800192a0  mov     r14, [rsp+78h+arg_38]
0x1800192a8  xor     r13d, r13d
0x1800192ab  mov     rsi, [rsp+78h+arg_48]
0x1800192b3  mov     rbx, rcx
0x1800192b6  mov     [rdx], r13w
0x1800192ba  mov     rcx, r12
0x1800192bd  mov     [r9], r13w
0x1800192c1  mov     rbp, r9
0x1800192c4  mov     [rdi], r13w
0x1800192c8  mov     r15, rdx
0x1800192cb  mov     [r14], r13w
0x1800192cf  mov     [rsi], r13w
0x1800192d3  call    ?Enter@?$CCritSectWithResource@V?$CNamedElemList@VCHandleNotif@PnPServices@@@@@@QEAAXXZ; CCritSectWithResource<CNamedElemList<PnPServices::CHandleNotif>>::Enter(void)
0x1800192d8  test    byte ptr [rbx+30h], 2
0x1800192dc  jnz     loc_1800194A5
0x1800192e2  test    byte ptr [rbx+2Ch], 1
0x1800192e6  mov     [rsp+78h+arg_38], r13
0x1800192ee  jz      short loc_180019335
0x1800192f0  lea     r8, [rbx+150h]; unsigned __int16 *
0x1800192f7  cmp     [r8], r13w
0x1800192fb  jz      short loc_180019312
0x1800192fd  mov     edx, 110h; unsigned __int64
0x180019302  mov     rcx, r15; unsigned __int16 *
0x180019305  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001930a  test    eax, eax
0x18001930c  jns     short loc_180019312
0x18001930e  mov     [r15], r13w
0x180019312  lea     r8, [rbx+370h]; unsigned __int16 *
0x180019319  cmp     [r8], r13w
0x18001931d  jz      short loc_180019335
0x18001931f  mov     edx, 21h ; '!'; unsigned __int64
0x180019324  mov     rcx, rbp; unsigned __int16 *
0x180019327  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001932c  test    eax, eax
0x18001932e  jns     short loc_180019335
0x180019330  mov     [rbp+0], r13w
0x180019335  cmp     [rbx+0C84h], r13d
0x18001933c  jz      loc_1800194A5
0x180019342  lea     rcx, [rbx+10h]
0x180019346  mov     rax, rbx
0x180019349  neg     rax
0x18001934c  lea     r8, [rsp+78h+arg_38]; struct CRefCounted *
0x180019354  sbb     rdx, rdx
0x180019357  and     rdx, rcx; struct PnPHelper::CHWDeviceInst *
0x18001935a  lea     rcx, [rbx+0A58h]; this
0x180019361  call    ?CreatePnPDevicePropertiesObject@PnPHelper@@YAJPEAVCHWDeviceInst@1@PEAVCRefCounted@@PEAPEAVIDeviceProperties@Autoplay@@@Z; PnPHelper::CreatePnPDevicePropertiesObject(PnPHelper::CHWDeviceInst *,CRefCounted *,Autoplay::IDeviceProperties * *)
0x180019366  test    eax, eax
0x180019368  js      loc_1800194A5
0x18001936e  mov     rbx, [rsp+78h+arg_38]
0x180019376  lea     r8, [rsp+78h+arg_28]; unsigned __int16 *
0x18001937e  mov     rcx, rbx; this
0x180019381  mov     [rsp+78h+arg_28], r13
0x180019389  lea     rdx, aIcons; "Icons"
0x180019390  call    ?GetDevicePropertyAsMultiSz@Settings@@YAJPEAVIDeviceProperties@Autoplay@@PEBGPEAPEAU_WORD_BLOB@@@Z; Settings::GetDevicePropertyAsMultiSz(Autoplay::IDeviceProperties *,ushort const *,_WORD_BLOB * *)
0x180019395  test    eax, eax
0x180019397  js      short loc_1800193C5
0x180019399  mov     r10, [rsp+78h+arg_28]
0x1800193a1  mov     edx, 110h; unsigned __int64
0x1800193a6  mov     rcx, rdi; unsigned __int16 *
0x1800193a9  lea     r8, [r10+4]; unsigned __int16 *
0x1800193ad  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800193b2  test    eax, eax
0x1800193b4  jns     short loc_1800193BA
0x1800193b6  mov     [rdi], r13w
0x1800193ba  mov     rcx, r10; pv
0x1800193bd  call    cs:__imp_CoTaskMemFree
0x1800193c3  jmp     short loc_1800193C9
0x1800193c5  mov     [rdi], r13w
0x1800193c9  lea     r8, [rsp+78h+arg_28]; unsigned __int16 *
0x1800193d1  mov     rcx, rbx; this
0x1800193d4  lea     rdx, aNomediaicons; "NoMediaIcons"
0x1800193db  call    ?GetDevicePropertyAsMultiSz@Settings@@YAJPEAVIDeviceProperties@Autoplay@@PEBGPEAPEAU_WORD_BLOB@@@Z; Settings::GetDevicePropertyAsMultiSz(Autoplay::IDeviceProperties *,ushort const *,_WORD_BLOB * *)
0x1800193e0  test    eax, eax
0x1800193e2  js      short loc_180019410
0x1800193e4  mov     r10, [rsp+78h+arg_28]
0x1800193ec  mov     edx, 110h; unsigned __int64
0x1800193f1  mov     rcx, r14; unsigned __int16 *
0x1800193f4  lea     r8, [r10+4]; unsigned __int16 *
0x1800193f8  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800193fd  test    eax, eax
0x1800193ff  jns     short loc_180019405
0x180019401  mov     [r14], r13w
0x180019405  mov     rcx, r10; pv
0x180019408  call    cs:__imp_CoTaskMemFree
0x18001940e  jmp     short loc_180019414
0x180019410  mov     [r14], r13w
0x180019414  mov     rax, [rbx]
0x180019417  lea     rdi, aLabel; "Label"
0x18001941e  mov     r9d, 110h
0x180019424  mov     r8, rsi
0x180019427  mov     rdx, rdi
0x18001942a  mov     rcx, rbx
0x18001942d  mov     rax, [rax+18h]
0x180019431  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019436  mov     r14d, 80004005h
0x18001943c  cmp     eax, r14d
0x18001943f  jnz     short loc_180019495
0x180019441  mov     r15d, 1
0x180019447  mov     ebp, 220h
0x18001944c  mov     r8d, r15d; unsigned __int16 *
0x18001944f  mov     dword ptr [rsp+78h+var_58], ebp; unsigned __int8 *
0x180019453  mov     r9, rsi; unsigned int
0x180019456  mov     rdx, rdi; struct Autoplay::IDeviceProperties *
0x180019459  mov     rcx, rbx; this
0x18001945c  call    ?_GetMultiDeviceGroupPropertyData@Settings@@YAJPEAVIDeviceProperties@Autoplay@@PEBGKPEAEK@Z; Settings::_GetMultiDeviceGroupPropertyData(Autoplay::IDeviceProperties *,ushort const *,ulong,uchar *,ulong)
0x180019461  cmp     eax, r14d
0x180019464  jnz     short loc_180019495
0x180019466  mov     r9, rsi; unsigned int
0x180019469  mov     dword ptr [rsp+78h+var_58], ebp; unsigned __int8 *
0x18001946d  mov     r8d, r15d; unsigned __int16 *
0x180019470  mov     rdx, rdi; struct Autoplay::IDeviceProperties *
0x180019473  mov     rcx, rbx; this
0x180019476  call    ?_GetDeviceGroupPropertyData@Settings@@YAJPEAVIDeviceProperties@Autoplay@@PEBGKPEAEK@Z; Settings::_GetDeviceGroupPropertyData(Autoplay::IDeviceProperties *,ushort const *,ulong,uchar *,ulong)
0x18001947b  cmp     eax, r14d
0x18001947e  jnz     short loc_180019495
0x180019480  mov     r9, rsi; unsigned int
0x180019483  mov     dword ptr [rsp+78h+var_58], ebp; unsigned __int8 *
0x180019487  mov     r8d, r15d; unsigned __int16 *
0x18001948a  mov     rdx, rdi; struct Autoplay::IDeviceProperties *
0x18001948d  mov     rcx, rbx; this
0x180019490  call    ?_GetDeviceClassPropertyData@Settings@@YAJPEAVIDeviceProperties@Autoplay@@PEBGKPEAEK@Z; Settings::_GetDeviceClassPropertyData(Autoplay::IDeviceProperties *,ushort const *,ulong,uchar *,ulong)
0x180019495  test    eax, eax
0x180019497  jns     short loc_18001949D
0x180019499  mov     [rsi], r13w
0x18001949d  mov     rcx, rbx; this
0x1800194a0  call    ?Release@CRefCounted@@QEBAKXZ; CRefCounted::Release(void)
0x1800194a5  mov     rcx, r12
0x1800194a8  call    ?Leave@?$CCritSectWithResource@VCDummyResource@@@@QEAAXXZ; CCritSectWithResource<CDummyResource>::Leave(void)
0x1800194ad  xor     eax, eax
0x1800194af  add     rsp, 38h
0x1800194b3  pop     r15
0x1800194b5  pop     r14
0x1800194b7  pop     r13
0x1800194b9  pop     r12
0x1800194bb  pop     rdi
0x1800194bc  pop     rsi
0x1800194bd  pop     rbp
0x1800194be  pop     rbx
0x1800194bf  retn
```
