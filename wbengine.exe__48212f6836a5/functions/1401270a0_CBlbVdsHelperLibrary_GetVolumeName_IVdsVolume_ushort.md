# CBlbVdsHelperLibrary::GetVolumeName(IVdsVolume *,ushort * *)

- ea: `0x1401270a0`
- end: `0x14012738e`
- name: `?GetVolumeName@CBlbVdsHelperLibrary@@AEAAJPEAUIVdsVolume@@PEAPEAG@Z`
- size: `750`
- prototype: `__int64 __fastcall(CBlbVdsHelperLibrary *__hidden this, struct IVdsVolume *, unsigned __int16 **)`
- caller_count: `4`
- callee_count: `10`
- tags: `reparse_path, service_task`

## callers

- `0x140124f8c`
- `0x1401267f0`
- `0x140128780`
- `0x140128bc0`

## callees

- `0x140006ca8`
- `0x140007ad3`
- `0x14000bb24`
- `0x14000bb4c`
- `0x140014200`
- `0x140014260`
- `0x14008863c`
- `0x140124cdc`
- `0x1401270a0`
- `0x140137010`

## import_xrefs

- `KERNEL32!GetVolumeNameForVolumeMountPointW` at `0x140127300`
- `KERNEL32!GetVolumeNameForVolumeMountPointW` at `0x140127300`
- `KERNEL32!GetLastError` at `0x14012730a`
- `KERNEL32!GetLastError` at `0x14012730a`
- `ole32!CoTaskMemAlloc` at `0x1401270e1`
- `ole32!CoTaskMemAlloc` at `0x1401272c1`
- `ole32!CoTaskMemAlloc` at `0x1401270e1`
- `ole32!CoTaskMemAlloc` at `0x1401272c1`
- `ole32!CoTaskMemFree` at `0x1401272d4`
- `ole32!CoTaskMemFree` at `0x14012735a`
- `ole32!CoTaskMemFree` at `0x14012736d`
- `ole32!CoTaskMemFree` at `0x1401272d4`
- `ole32!CoTaskMemFree` at `0x14012735a`
- `ole32!CoTaskMemFree` at `0x14012736d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CBlbVdsHelperLibrary::GetVolumeName(
        CBlbVdsHelperLibrary *this,
        struct IVdsVolume *a2,
        unsigned __int16 **a3)
{
  const unsigned __int16 **v5; // rbx
  int v6; // r9d
  int v7; // eax
  PVOID *v8; // rcx
  signed int appended; // ebx
  unsigned __int16 *v10; // rax
  unsigned __int16 *v11; // rbp
  signed int LastError; // eax
  void *v13; // rcx
  LPVOID pv; // [rsp+50h] [rbp+8h] BYREF
  const unsigned __int16 **v16; // [rsp+58h] [rbp+10h] BYREF

  pv = this;
  if ( !a3 )
    BlbAssert("base\\stor\\blb\\wsbutil\\wsbvdshelperlibrary.cpp", 0x930u, "pwszVolumeName");
  *a3 = 0;
  v5 = (const unsigned __int16 **)CoTaskMemAlloc(0x38u);
  v16 = v5;
  *(_OWORD *)v5 = 0;
  *((_OWORD *)v5 + 1) = 0;
  *((_OWORD *)v5 + 2) = 0;
  v5[6] = 0;
  if ( ((int (__fastcall *)(struct IVdsVolume *, const unsigned __int16 **))a2->lpVtbl->GetProperties)(a2, v5) < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 116, WPP_a6dd3b05e291303603dc788acefb07d7_Traceguids);
    }
    goto LABEL_30;
  }
  v6 = *((_DWORD *)v5 + 5);
  if ( v6 != 1 && v6 != 4 || (v7 = *((_DWORD *)v5 + 6), v7 != 1) && (unsigned int)(v7 - 4) > 1 || !v5[6] )
  {
    v8 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 117, WPP_a6dd3b05e291303603dc788acefb07d7_Traceguids);
        v8 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 1) != 0 && *((_BYTE *)v8 + 25) >= 4u )
      {
        WPP_SF_d(v8[2], 118, WPP_a6dd3b05e291303603dc788acefb07d7_Traceguids);
        v8 = (PVOID *)WPP_GLOBAL_Control;
      }
    }
    if ( !v5[6] )
    {
      if ( v8 == &WPP_GLOBAL_Control )
      {
LABEL_30:
        appended = -2139619229;
        goto LABEL_48;
      }
      if ( (*((_BYTE *)v8 + 28) & 1) != 0 && *((_BYTE *)v8 + 25) >= 4u )
      {
        WPP_SF_(v8[2], 119, WPP_a6dd3b05e291303603dc788acefb07d7_Traceguids);
        v8 = (PVOID *)WPP_GLOBAL_Control;
      }
    }
    if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 1) != 0 && *((_BYTE *)v8 + 25) >= 3u )
      WPP_SF_(v8[2], 120, WPP_a6dd3b05e291303603dc788acefb07d7_Traceguids);
    goto LABEL_30;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 121, WPP_a6dd3b05e291303603dc788acefb07d7_Traceguids, v5[6]);
  }
  pv = 0;
  appended = BlbutilAppendString(v5[6], L"\\", (unsigned __int16 **)&pv);
  if ( appended >= 0 )
  {
    v10 = (unsigned __int16 *)CoTaskMemAlloc(0x64u);
    v11 = v10;
    if ( v10 )
    {
      memset_0(v10, 0, 0x64u);
      if ( GetVolumeNameForVolumeMountPointW((LPCWSTR)pv, v11, 0x32u) )
      {
        *a3 = v11;
        v13 = pv;
      }
      else
      {
        LastError = GetLastError();
        appended = LastError;
        if ( LastError > 0 )
          appended = (unsigned __int16)LastError | 0x80070000;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_Sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            122,
            (unsigned int)WPP_a6dd3b05e291303603dc788acefb07d7_Traceguids,
            (_DWORD)pv,
            appended);
        }
        CoTaskMemFree(pv);
        v13 = v11;
      }
      CoTaskMemFree(v13);
    }
    else
    {
      CoTaskMemFree(pv);
      appended = -2147024882;
    }
  }
LABEL_48:
  VDS_VOLUME_PROP_SMART<_VDS_VOLUME_PROP>::~VDS_VOLUME_PROP_SMART<_VDS_VOLUME_PROP>((void **)&v16);
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x1401270a0  mov     [rsp+arg_10], rbx
0x1401270a5  mov     [rsp+pv], rcx
0x1401270aa  push    rbp
0x1401270ab  push    rdi
0x1401270ac  push    r15
0x1401270ae  sub     rsp, 30h
0x1401270b2  mov     r15, r8
0x1401270b5  mov     rdi, rdx
0x1401270b8  test    r8, r8
0x1401270bb  jnz     short loc_1401270D5
0x1401270bd  lea     r8, aPwszvolumename; "pwszVolumeName"
0x1401270c4  mov     edx, 930h; unsigned int
0x1401270c9  lea     rcx, aBaseStorBlbWsb_6; "base\\stor\\blb\\wsbutil\\wsbvdshelperl"...
0x1401270d0  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x1401270d5  mov     qword ptr [r15], 0
0x1401270dc  mov     ecx, 38h ; '8'; cb
0x1401270e1  call    cs:__imp_CoTaskMemAlloc
0x1401270e7  mov     rbx, rax
0x1401270ea  mov     [rsp+48h+arg_8], rax
0x1401270ef  xorps   xmm0, xmm0
0x1401270f2  xor     eax, eax
0x1401270f4  movups  xmmword ptr [rbx], xmm0
0x1401270f7  movups  xmmword ptr [rbx+10h], xmm0
0x1401270fb  movups  xmmword ptr [rbx+20h], xmm0
0x1401270ff  mov     [rbx+30h], rax
0x140127103  mov     rax, [rdi]
0x140127106  mov     rdx, rbx
0x140127109  mov     rcx, rdi
0x14012710c  mov     rax, [rax+18h]
0x140127110  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140127115  test    eax, eax
0x140127117  jns     short loc_140127161
0x140127119  lea     rdi, WPP_GLOBAL_Control
0x140127120  mov     rcx, cs:WPP_GLOBAL_Control
0x140127127  cmp     rcx, rdi
0x14012712a  jz      loc_140127252
0x140127130  test    byte ptr [rcx+1Ch], 1
0x140127134  jz      loc_140127252
0x14012713a  cmp     byte ptr [rcx+19h], 2
0x14012713e  jb      loc_140127252
0x140127144  mov     edx, 74h ; 't'
0x140127149  mov     r9d, eax
0x14012714c  lea     r8, WPP_a6dd3b05e291303603dc788acefb07d7_Traceguids
0x140127153  mov     rcx, [rcx+10h]
0x140127157  call    WPP_SF_d
0x14012715c  jmp     loc_140127252
0x140127161  mov     r9d, [rbx+14h]
0x140127165  cmp     r9d, 1
0x140127169  jz      short loc_140127171
0x14012716b  cmp     r9d, 4
0x14012716f  jnz     short loc_14012718C
0x140127171  mov     eax, [rbx+18h]
0x140127174  cmp     eax, 1
0x140127177  jz      short loc_140127181
0x140127179  add     eax, 0FFFFFFFCh
0x14012717c  cmp     eax, 1
0x14012717f  ja      short loc_14012718C
0x140127181  cmp     qword ptr [rbx+30h], 0
0x140127186  jnz     loc_14012725C
0x14012718c  lea     rdi, WPP_GLOBAL_Control
0x140127193  mov     rcx, cs:WPP_GLOBAL_Control
0x14012719a  cmp     rcx, rdi
0x14012719d  jz      short loc_1401271F8
0x14012719f  test    byte ptr [rcx+1Ch], 1
0x1401271a3  jz      short loc_1401271C7
0x1401271a5  cmp     byte ptr [rcx+19h], 4
0x1401271a9  jb      short loc_1401271C7
0x1401271ab  mov     edx, 75h ; 'u'
0x1401271b0  lea     r8, WPP_a6dd3b05e291303603dc788acefb07d7_Traceguids
0x1401271b7  mov     rcx, [rcx+10h]
0x1401271bb  call    WPP_SF_d
0x1401271c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1401271c7  cmp     rcx, rdi
0x1401271ca  jz      short loc_1401271F8
0x1401271cc  test    byte ptr [rcx+1Ch], 1
0x1401271d0  jz      short loc_1401271F8
0x1401271d2  cmp     byte ptr [rcx+19h], 4
0x1401271d6  jb      short loc_1401271F8
0x1401271d8  mov     edx, 76h ; 'v'
0x1401271dd  mov     r9d, [rbx+18h]
0x1401271e1  lea     r8, WPP_a6dd3b05e291303603dc788acefb07d7_Traceguids
0x1401271e8  mov     rcx, [rcx+10h]
0x1401271ec  call    WPP_SF_d
0x1401271f1  mov     rcx, cs:WPP_GLOBAL_Control
0x1401271f8  cmp     qword ptr [rbx+30h], 0
0x1401271fd  jnz     short loc_14012722C
0x1401271ff  cmp     rcx, rdi
0x140127202  jz      short loc_140127252
0x140127204  test    byte ptr [rcx+1Ch], 1
0x140127208  jz      short loc_14012722C
0x14012720a  cmp     byte ptr [rcx+19h], 4
0x14012720e  jb      short loc_14012722C
0x140127210  mov     edx, 77h ; 'w'
0x140127215  lea     r8, WPP_a6dd3b05e291303603dc788acefb07d7_Traceguids
0x14012721c  mov     rcx, [rcx+10h]
0x140127220  call    WPP_SF_
0x140127225  mov     rcx, cs:WPP_GLOBAL_Control
0x14012722c  cmp     rcx, rdi
0x14012722f  jz      short loc_140127252
0x140127231  test    byte ptr [rcx+1Ch], 1
0x140127235  jz      short loc_140127252
0x140127237  cmp     byte ptr [rcx+19h], 3
0x14012723b  jb      short loc_140127252
0x14012723d  mov     edx, 78h ; 'x'
0x140127242  lea     r8, WPP_a6dd3b05e291303603dc788acefb07d7_Traceguids
0x140127249  mov     rcx, [rcx+10h]
0x14012724d  call    WPP_SF_
0x140127252  mov     ebx, 80780063h
0x140127257  jmp     loc_140127374
0x14012725c  lea     rdi, WPP_GLOBAL_Control
0x140127263  mov     rcx, cs:WPP_GLOBAL_Control
0x14012726a  cmp     rcx, rdi
0x14012726d  jz      short loc_140127294
0x14012726f  test    byte ptr [rcx+1Ch], 1
0x140127273  jz      short loc_140127294
0x140127275  cmp     byte ptr [rcx+19h], 4
0x140127279  jb      short loc_140127294
0x14012727b  mov     edx, 79h ; 'y'
0x140127280  mov     r9, [rbx+30h]
0x140127284  lea     r8, WPP_a6dd3b05e291303603dc788acefb07d7_Traceguids
0x14012728b  mov     rcx, [rcx+10h]
0x14012728f  call    WPP_SF_S
0x140127294  mov     [rsp+48h+pv], 0
0x14012729d  lea     r8, [rsp+48h+pv]; unsigned __int16 **
0x1401272a2  lea     rdx, asc_14013C090; "\\"
0x1401272a9  mov     rcx, [rbx+30h]; unsigned __int16 *
0x1401272ad  call    ?BlbutilAppendString@@YAJPEBG0PEAPEAG@Z; BlbutilAppendString(ushort const *,ushort const *,ushort * *)
0x1401272b2  mov     ebx, eax
0x1401272b4  test    eax, eax
0x1401272b6  js      loc_140127374
0x1401272bc  mov     ecx, 64h ; 'd'; cb
0x1401272c1  call    cs:__imp_CoTaskMemAlloc
0x1401272c7  mov     rbp, rax
0x1401272ca  test    rax, rax
0x1401272cd  jnz     short loc_1401272E4
0x1401272cf  mov     rcx, [rsp+48h+pv]; pv
0x1401272d4  call    cs:__imp_CoTaskMemFree
0x1401272da  mov     ebx, 8007000Eh
0x1401272df  jmp     loc_140127374
0x1401272e4  xor     edx, edx; Val
0x1401272e6  lea     r8d, [rdx+64h]; Size
0x1401272ea  mov     rcx, rbp; void *
0x1401272ed  call    memset_0
0x1401272f2  mov     r8d, 32h ; '2'; cchBufferLength
0x1401272f8  mov     rdx, rbp; lpszVolumeName
0x1401272fb  mov     rcx, [rsp+48h+pv]; lpszVolumeMountPoint
0x140127300  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x140127306  test    eax, eax
0x140127308  jnz     short loc_140127365
0x14012730a  call    cs:__imp_GetLastError
0x140127310  mov     ebx, eax
0x140127312  test    eax, eax
0x140127314  jle     short loc_14012731F
0x140127316  movzx   ebx, ax
0x140127319  or      ebx, 80070000h
0x14012731f  mov     rcx, cs:WPP_GLOBAL_Control
0x140127326  cmp     rcx, rdi
0x140127329  jz      short loc_140127355
0x14012732b  test    byte ptr [rcx+1Ch], 1
0x14012732f  jz      short loc_140127355
0x140127331  cmp     byte ptr [rcx+19h], 2
0x140127335  jb      short loc_140127355
0x140127337  mov     edx, 7Ah ; 'z'
0x14012733c  mov     [rsp+48h+var_28], ebx
0x140127340  mov     r9, [rsp+48h+pv]
0x140127345  lea     r8, WPP_a6dd3b05e291303603dc788acefb07d7_Traceguids
0x14012734c  mov     rcx, [rcx+10h]
0x140127350  call    WPP_SF_Sd
0x140127355  mov     rcx, [rsp+48h+pv]; pv
0x14012735a  call    cs:__imp_CoTaskMemFree
0x140127360  mov     rcx, rbp
0x140127363  jmp     short loc_14012736D
0x140127365  mov     [r15], rbp
0x140127368  mov     rcx, [rsp+48h+pv]; pv
0x14012736d  call    cs:__imp_CoTaskMemFree
0x140127373  nop
0x140127374  lea     rcx, [rsp+48h+arg_8]
0x140127379  call    ??1?$VDS_VOLUME_PROP_SMART@U_VDS_VOLUME_PROP@@@@QEAA@XZ; VDS_VOLUME_PROP_SMART<_VDS_VOLUME_PROP>::~VDS_VOLUME_PROP_SMART<_VDS_VOLUME_PROP>(void)
0x14012737e  mov     eax, ebx
0x140127380  mov     rbx, [rsp+48h+arg_10]
0x140127385  add     rsp, 30h
0x140127389  pop     r15
0x14012738b  pop     rdi
0x14012738c  pop     rbp
0x14012738d  retn
```
