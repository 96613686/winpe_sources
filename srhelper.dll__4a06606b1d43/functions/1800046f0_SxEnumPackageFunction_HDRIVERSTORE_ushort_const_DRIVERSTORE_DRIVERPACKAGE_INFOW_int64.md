# SxEnumPackageFunction(HDRIVERSTORE__ *,ushort const *,_DRIVERSTORE_DRIVERPACKAGE_INFOW *,__int64)

- ea: `0x1800046f0`
- end: `0x180004922`
- name: `?SxEnumPackageFunction@@YAHPEAUHDRIVERSTORE__@@PEBGPEAU_DRIVERSTORE_DRIVERPACKAGE_INFOW@@_J@Z`
- size: `562`
- prototype: `__int64 __fastcall(struct HDRIVERSTORE__ *, const unsigned __int16 *, struct _DRIVERSTORE_DRIVERPACKAGE_INFOW *, __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task`

## callees

- `0x180003d08`
- `0x1800046f0`
- `0x180004928`
- `0x1800157be`
- `0x1800157f0`
- `0x180016010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180004774`
- `KERNEL32!GetLastError` at `0x1800047e3`
- `KERNEL32!GetLastError` at `0x180004774`
- `KERNEL32!GetLastError` at `0x1800047e3`
- `ole32!CoTaskMemFree` at `0x1800048f7`
- `ole32!CoTaskMemFree` at `0x1800048f7`
- `drvstore!DriverStoreDriverPackageResolveCallbackW` at `0x180004735`
- `drvstore!DriverPackageOpenW` at `0x180004766`
- `drvstore!DriverPackageOpenW` at `0x180004766`
- `drvstore!DriverPackageGetVersionInfoW` at `0x1800047d9`
- `drvstore!DriverPackageGetVersionInfoW` at `0x1800047d9`
- `drvstore!DriverPackageClose` at `0x1800048ee`
- `drvstore!DriverPackageClose` at `0x1800048ee`

## pseudocode

```c
__int64 __fastcall SxEnumPackageFunction(
        struct HDRIVERSTORE__ *a1,
        const unsigned __int16 *a2,
        struct _DRIVERSTORE_DRIVERPACKAGE_INFOW *a3,
        __int64 a4)
{
  unsigned int v8; // r15d
  __int64 v9; // rdx
  unsigned __int16 *v10; // rdi
  __int64 v11; // rax
  __int64 v12; // rbp
  signed int LastError; // eax
  char v14; // cl
  _QWORD *v15; // r10
  int v16; // edx
  int v17; // ebx
  signed int v18; // eax
  int DriverName; // eax
  unsigned __int16 *v21; // [rsp+30h] [rbp-758h] BYREF
  _QWORD v22[3]; // [rsp+38h] [rbp-750h] BYREF
  _DWORD v23[444]; // [rsp+50h] [rbp-738h] BYREF

  v8 = 0;
  memset_0(v23, 0, sizeof(v23));
  v9 = *(unsigned __int16 *)a3;
  v10 = 0;
  v22[0] = DriverStoreDriverPackageResolveCallbackW;
  v21 = 0;
  v22[1] = a1;
  v11 = DriverPackageOpenW(a2, v9, 0, 1, v22);
  v12 = v11;
  if ( !v11 )
  {
    LastError = GetLastError();
    v14 = LastError;
    if ( LastError > 0 )
      v14 = LastError;
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x4000000) == 0 )
      goto LABEL_8;
    v16 = 21;
LABEL_7:
    WPP_SF_SD(v15[2], v16, (unsigned int)WPP_012e94a410f034635dd5ee797f3d6253_Traceguids, (_DWORD)a2, v14);
LABEL_8:
    v17 = 0;
    goto LABEL_27;
  }
  v23[0] = 1776;
  if ( !(unsigned int)DriverPackageGetVersionInfoW(v11, v23) )
  {
    v18 = GetLastError();
    v14 = v18;
    if ( v18 > 0 )
      v14 = v18;
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x4000000) == 0 )
      goto LABEL_8;
    v16 = 22;
    goto LABEL_7;
  }
  DriverName = SxGetDriverName((struct _DRIVERPACKAGE_VERSION_INFOW *)v23, a3, &v21);
  if ( DriverName >= 0 )
  {
    v10 = v21;
    v17 = (*(__int64 (__fastcall **)(_QWORD, __int64, unsigned __int16 *))a4)(*(_QWORD *)(a4 + 8), 2, v21);
    if ( v17 >= 0 )
    {
      if ( v17 == 1 )
        v17 = -2147467260;
      else
        v8 = 1;
    }
    else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
           && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000000) != 0 )
    {
      WPP_SF_SD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        24,
        (unsigned int)WPP_012e94a410f034635dd5ee797f3d6253_Traceguids,
        (_DWORD)a2,
        v17);
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x4000000) != 0 )
      WPP_SF_SD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        23,
        (unsigned int)WPP_012e94a410f034635dd5ee797f3d6253_Traceguids,
        (_DWORD)a2,
        DriverName);
    v10 = v21;
    v17 = 0;
  }
LABEL_27:
  *(_DWORD *)(a4 + 16) = v17;
  if ( v12 )
    DriverPackageClose(v12);
  CoTaskMemFree(v10);
  return v8;
}

```

## disassembly

```asm
0x1800046f0  push    rbx
0x1800046f2  push    rbp
0x1800046f3  push    rsi
0x1800046f4  push    rdi
0x1800046f5  push    r12
0x1800046f7  push    r14
0x1800046f9  push    r15
0x1800046fb  sub     rsp, 750h
0x180004702  mov     rax, cs:__security_cookie
0x180004709  xor     rax, rsp
0x18000470c  mov     [rsp+788h+var_48], rax
0x180004714  mov     r12, r8
0x180004717  mov     rsi, rdx
0x18000471a  mov     rbx, rcx
0x18000471d  xor     edx, edx; Val
0x18000471f  mov     r8d, 6F0h; Size
0x180004725  lea     rcx, [rsp+788h+var_738]; void *
0x18000472a  mov     r14, r9
0x18000472d  xor     r15d, r15d
0x180004730  call    memset_0
0x180004735  mov     rax, cs:__imp_DriverStoreDriverPackageResolveCallbackW
0x18000473c  lea     r9d, [r15+1]
0x180004740  movzx   edx, word ptr [r12]
0x180004745  xor     edi, edi
0x180004747  mov     [rsp+788h+var_750], rax
0x18000474c  xor     r8d, r8d
0x18000474f  lea     rax, [rsp+788h+var_750]
0x180004754  mov     [rsp+788h+var_758], rdi
0x180004759  mov     rcx, rsi
0x18000475c  mov     [rsp+788h+var_768], rax
0x180004761  mov     [rsp+788h+var_748], rbx
0x180004766  call    cs:__imp_DriverPackageOpenW
0x18000476c  mov     rbp, rax
0x18000476f  test    rax, rax
0x180004772  jnz     short loc_1800047C9
0x180004774  call    cs:__imp_GetLastError
0x18000477a  mov     ecx, eax
0x18000477c  test    eax, eax
0x18000477e  jle     short loc_180004789
0x180004780  movzx   ecx, ax
0x180004783  or      ecx, 80070000h
0x180004789  mov     r10, cs:WPP_GLOBAL_Control
0x180004790  lea     rax, WPP_GLOBAL_Control
0x180004797  cmp     r10, rax
0x18000479a  jz      short loc_1800047C2
0x18000479c  test    dword ptr [r10+1Ch], 4000000h
0x1800047a4  jz      short loc_1800047C2
0x1800047a6  mov     edx, 15h
0x1800047ab  mov     dword ptr [rsp+788h+var_768], ecx
0x1800047af  lea     r8, WPP_012e94a410f034635dd5ee797f3d6253_Traceguids
0x1800047b6  mov     rcx, [r10+10h]
0x1800047ba  mov     r9, rsi
0x1800047bd  call    WPP_SF_SD
0x1800047c2  xor     ebx, ebx
0x1800047c4  jmp     loc_1800048E2
0x1800047c9  lea     rdx, [rsp+788h+var_738]
0x1800047ce  mov     [rsp+788h+var_738], 6F0h
0x1800047d6  mov     rcx, rbp
0x1800047d9  call    cs:__imp_DriverPackageGetVersionInfoW
0x1800047df  test    eax, eax
0x1800047e1  jnz     short loc_18000481C
0x1800047e3  call    cs:__imp_GetLastError
0x1800047e9  mov     ecx, eax
0x1800047eb  test    eax, eax
0x1800047ed  jle     short loc_1800047F8
0x1800047ef  movzx   ecx, ax
0x1800047f2  or      ecx, 80070000h
0x1800047f8  mov     r10, cs:WPP_GLOBAL_Control
0x1800047ff  lea     rax, WPP_GLOBAL_Control
0x180004806  cmp     r10, rax
0x180004809  jz      short loc_1800047C2
0x18000480b  test    dword ptr [r10+1Ch], 4000000h
0x180004813  jz      short loc_1800047C2
0x180004815  mov     edx, 16h
0x18000481a  jmp     short loc_1800047AB
0x18000481c  lea     r8, [rsp+788h+var_758]; unsigned __int16 **
0x180004821  mov     rdx, r12; struct _DRIVERSTORE_DRIVERPACKAGE_INFOW *
0x180004824  lea     rcx, [rsp+788h+var_738]; struct _DRIVERPACKAGE_VERSION_INFOW *
0x180004829  call    ?SxGetDriverName@@YAJPEAU_DRIVERPACKAGE_VERSION_INFOW@@PEAU_DRIVERSTORE_DRIVERPACKAGE_INFOW@@PEAPEAG@Z; SxGetDriverName(_DRIVERPACKAGE_VERSION_INFOW *,_DRIVERSTORE_DRIVERPACKAGE_INFOW *,ushort * *)
0x18000482e  mov     r8d, eax
0x180004831  test    eax, eax
0x180004833  jns     short loc_180004877
0x180004835  mov     rcx, cs:WPP_GLOBAL_Control
0x18000483c  lea     rax, WPP_GLOBAL_Control
0x180004843  cmp     rcx, rax
0x180004846  jz      short loc_18000486E
0x180004848  test    dword ptr [rcx+1Ch], 4000000h
0x18000484f  jz      short loc_18000486E
0x180004851  mov     rcx, [rcx+10h]
0x180004855  mov     edx, 17h
0x18000485a  mov     dword ptr [rsp+788h+var_768], r8d
0x18000485f  mov     r9, rsi
0x180004862  lea     r8, WPP_012e94a410f034635dd5ee797f3d6253_Traceguids
0x180004869  call    WPP_SF_SD
0x18000486e  mov     rdi, [rsp+788h+var_758]
0x180004873  xor     ebx, ebx
0x180004875  jmp     short loc_1800048E2
0x180004877  mov     rdi, [rsp+788h+var_758]
0x18000487c  mov     edx, 2
0x180004881  mov     rcx, [r14+8]
0x180004885  mov     r8, rdi
0x180004888  mov     rax, [r14]
0x18000488b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004890  mov     ebx, eax
0x180004892  test    eax, eax
0x180004894  jns     short loc_1800048D0
0x180004896  mov     rcx, cs:WPP_GLOBAL_Control
0x18000489d  lea     rax, WPP_GLOBAL_Control
0x1800048a4  cmp     rcx, rax
0x1800048a7  jz      short loc_1800048E2
0x1800048a9  test    dword ptr [rcx+1Ch], 2000000h
0x1800048b0  jz      short loc_1800048E2
0x1800048b2  mov     rcx, [rcx+10h]
0x1800048b6  lea     r8, WPP_012e94a410f034635dd5ee797f3d6253_Traceguids
0x1800048bd  mov     edx, 18h
0x1800048c2  mov     dword ptr [rsp+788h+var_768], ebx
0x1800048c6  mov     r9, rsi
0x1800048c9  call    WPP_SF_SD
0x1800048ce  jmp     short loc_1800048E2
0x1800048d0  cmp     ebx, 1
0x1800048d3  jnz     short loc_1800048DC
0x1800048d5  mov     ebx, 80004004h
0x1800048da  jmp     short loc_1800048E2
0x1800048dc  mov     r15d, 1
0x1800048e2  mov     [r14+10h], ebx
0x1800048e6  test    rbp, rbp
0x1800048e9  jz      short loc_1800048F4
0x1800048eb  mov     rcx, rbp
0x1800048ee  call    cs:__imp_DriverPackageClose
0x1800048f4  mov     rcx, rdi; pv
0x1800048f7  call    cs:__imp_CoTaskMemFree
0x1800048fd  mov     eax, r15d
0x180004900  mov     rcx, [rsp+788h+var_48]
0x180004908  xor     rcx, rsp; StackCookie
0x18000490b  call    __security_check_cookie
0x180004910  add     rsp, 750h
0x180004917  pop     r15
0x180004919  pop     r14
0x18000491b  pop     r12
0x18000491d  pop     rdi
0x18000491e  pop     rsi
0x18000491f  pop     rbp
0x180004920  pop     rbx
0x180004921  retn
```
