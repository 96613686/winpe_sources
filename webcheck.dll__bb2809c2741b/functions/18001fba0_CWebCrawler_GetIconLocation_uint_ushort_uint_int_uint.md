# CWebCrawler::GetIconLocation(uint,ushort *,uint,int *,uint *)

- ea: `0x18001fba0`
- end: `0x18001fdc1`
- name: `?GetIconLocation@CWebCrawler@@UEAAJIPEAGIPEAHPEAI@Z`
- size: `545`
- prototype: `int(CWebCrawler *__hidden this, unsigned int, unsigned __int16 *, unsigned int, int *, unsigned int *)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180003950`
- `0x18000c740`
- `0x18001fba0`
- `0x18002a010`

## import_xrefs

- `KERNEL32!LocalAlloc` at `0x18001fc0f`
- `KERNEL32!LocalAlloc` at `0x18001fc0f`
- `ole32!CoCreateInstance` at `0x18001fcb8`
- `ole32!CoCreateInstance` at `0x18001fcfe`
- `ole32!CoCreateInstance` at `0x18001fcb8`
- `ole32!CoCreateInstance` at `0x18001fcfe`
- `ole32!CoUninitialize` at `0x18001fd9a`
- `ole32!CoUninitialize` at `0x18001fd9a`
- `ole32!CoInitialize` at `0x18001fcd0`
- `ole32!CoInitialize` at `0x18001fcd0`

## pseudocode

```c
__int64 __fastcall CWebCrawler::GetIconLocation(
        CWebCrawler *this,
        __int64 a2,
        unsigned __int16 *a3,
        unsigned int a4,
        int *a5,
        unsigned int *a6)
{
  int v6; // r13d
  unsigned __int64 v7; // r12
  int *v10; // r14
  unsigned int *v11; // r15
  HRESULT v12; // ebx
  struct OOEBuf *v13; // rax
  __int64 result; // rax
  __int64 v15; // rcx
  HRESULT v16; // eax
  LPVOID ppv; // [rsp+40h] [rbp-10h] BYREF
  __int64 v18; // [rsp+48h] [rbp-8h] BYREF
  unsigned int v19; // [rsp+98h] [rbp+48h]
  unsigned int v20; // [rsp+A0h] [rbp+50h] BYREF

  v19 = a2;
  v6 = 0;
  v7 = a4;
  ppv = 0;
  v18 = 0;
  if ( !a3 )
    return 2147942487LL;
  v10 = a5;
  if ( !a5 )
    return 2147942487LL;
  v11 = a6;
  if ( !a6 )
    return 2147942487LL;
  *a3 = 0;
  v12 = 0;
  *v10 = -1;
  if ( *((_QWORD *)this + 3) )
    goto LABEL_9;
  v13 = (struct OOEBuf *)LocalAlloc(0x40u, 0x1590u);
  *((_QWORD *)this + 3) = v13;
  if ( !v13 )
    return 2147942414LL;
  v20 = 0;
  result = LoadWithCookie(0, v13, &v20, (struct _GUID *)this + 4);
  v12 = result;
  if ( (int)result >= 0 )
  {
    a2 = v19;
LABEL_9:
    if ( *(_DWORD *)(*((_QWORD *)this + 3) + 40LL) )
    {
      StringCchCopyW(a3, v7, L":desktop:");
    }
    else
    {
      v15 = *((_QWORD *)this + 33);
      if ( v15 )
      {
        return (unsigned int)(*(__int64 (__fastcall **)(__int64, __int64, unsigned __int16 *, _QWORD, int *, unsigned int *))(*(_QWORD *)v15 + 24LL))(
                               v15,
                               a2,
                               a3,
                               (unsigned int)v7,
                               v10,
                               v11);
      }
      else
      {
        v16 = CoCreateInstance(&CLSID_InternetShortcut, 0, 1u, &IID_IUniformResourceLocatorW, &ppv);
        v12 = v16;
        if ( (v16 == -2147221008 || v16 == -2147221163) && CoInitialize(0) >= 0 )
        {
          v6 = 1;
          v12 = CoCreateInstance(&CLSID_InternetShortcut, 0, 1u, &IID_IUniformResourceLocatorW, &ppv);
        }
        if ( v12 >= 0 )
        {
          v12 = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64))(*(_QWORD *)ppv + 24LL))(
                  ppv,
                  *((_QWORD *)this + 3) + 556LL,
                  1);
          if ( v12 >= 0 )
          {
            v12 = (**(__int64 (__fastcall ***)(LPVOID, GUID *, __int64 *))ppv)(ppv, &IID_IExtractIconW, &v18);
            if ( v12 >= 0 )
            {
              v12 = (*(__int64 (__fastcall **)(__int64, _QWORD, unsigned __int16 *, _QWORD, int *, unsigned int *))(*(_QWORD *)v18 + 24LL))(
                      v18,
                      v19,
                      a3,
                      (unsigned int)v7,
                      v10,
                      v11);
              *((_QWORD *)this + 33) = v18;
            }
          }
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
        }
        if ( v6 )
          CoUninitialize();
      }
    }
    return (unsigned int)v12;
  }
  return result;
}

```

## disassembly

```asm
0x18001fba0  mov     [rsp-38h+arg_0], rbx
0x18001fba5  mov     [rsp-38h+arg_8], edx
0x18001fba9  push    rbp
0x18001fbaa  push    rsi
0x18001fbab  push    rdi
0x18001fbac  push    r12
0x18001fbae  push    r13
0x18001fbb0  push    r14
0x18001fbb2  push    r15
0x18001fbb4  mov     rbp, rsp
0x18001fbb7  sub     rsp, 50h
0x18001fbbb  xor     r13d, r13d
0x18001fbbe  mov     r12d, r9d
0x18001fbc1  mov     [rbp+var_10], r13
0x18001fbc5  mov     rsi, r8
0x18001fbc8  mov     [rbp+var_8], r13
0x18001fbcc  mov     rdi, rcx
0x18001fbcf  test    r8, r8
0x18001fbd2  jz      loc_18001FDA4
0x18001fbd8  mov     r14, [rbp+arg_20]
0x18001fbdc  test    r14, r14
0x18001fbdf  jz      loc_18001FDA4
0x18001fbe5  mov     r15, [rbp+arg_28]
0x18001fbe9  test    r15, r15
0x18001fbec  jz      loc_18001FDA4
0x18001fbf2  mov     [r8], r13w
0x18001fbf6  mov     ebx, r13d
0x18001fbf9  mov     dword ptr [r14], 0FFFFFFFFh
0x18001fc00  cmp     [rcx+18h], r13
0x18001fc04  jnz     short loc_18001FC4B
0x18001fc06  mov     edx, 1590h; uBytes
0x18001fc0b  lea     ecx, [r13+40h]; uFlags
0x18001fc0f  call    cs:__imp_LocalAlloc
0x18001fc15  mov     [rdi+18h], rax
0x18001fc19  test    rax, rax
0x18001fc1c  jnz     short loc_18001FC28
0x18001fc1e  mov     eax, 8007000Eh
0x18001fc23  jmp     loc_18001FDA9
0x18001fc28  lea     r9, [rdi+40h]; struct _GUID *
0x18001fc2c  mov     [rbp+arg_10], r13d
0x18001fc30  lea     r8, [rbp+arg_10]; unsigned int *
0x18001fc34  mov     rdx, rax; struct OOEBuf *
0x18001fc37  xor     ecx, ecx; psz2
0x18001fc39  call    ?LoadWithCookie@@YAJPEBGPEAUOOEBuf@@PEAKPEAU_GUID@@@Z; LoadWithCookie(ushort const *,OOEBuf *,ulong *,_GUID *)
0x18001fc3e  mov     ebx, eax
0x18001fc40  test    eax, eax
0x18001fc42  js      loc_18001FDA9
0x18001fc48  mov     edx, [rbp+arg_8]
0x18001fc4b  mov     rax, [rdi+18h]
0x18001fc4f  cmp     [rax+28h], r13d
0x18001fc53  jz      short loc_18001FC6C
0x18001fc55  mov     rdx, r12; unsigned __int64
0x18001fc58  lea     r8, aDesktop; ":desktop:"
0x18001fc5f  mov     rcx, rsi; unsigned __int16 *
0x18001fc62  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001fc67  jmp     loc_18001FDA0
0x18001fc6c  mov     rcx, [rdi+108h]
0x18001fc73  test    rcx, rcx
0x18001fc76  jz      short loc_18001FC9B
0x18001fc78  mov     rax, [rcx]
0x18001fc7b  mov     r9d, r12d
0x18001fc7e  mov     [rsp+50h+var_28], r15
0x18001fc83  mov     r8, rsi
0x18001fc86  mov     [rsp+50h+ppv], r14
0x18001fc8b  mov     rax, [rax+18h]
0x18001fc8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fc94  mov     ebx, eax
0x18001fc96  jmp     loc_18001FDA0
0x18001fc9b  xor     edx, edx; pUnkOuter
0x18001fc9d  lea     rax, [rbp+var_10]
0x18001fca1  lea     r9, IID_IUniformResourceLocatorW; riid
0x18001fca8  mov     [rsp+50h+ppv], rax; ppv
0x18001fcad  lea     rcx, CLSID_InternetShortcut; rclsid
0x18001fcb4  lea     r8d, [rdx+1]; dwClsContext
0x18001fcb8  call    cs:__imp_CoCreateInstance
0x18001fcbe  mov     ebx, eax
0x18001fcc0  cmp     eax, 800401F0h
0x18001fcc5  jz      short loc_18001FCCE
0x18001fcc7  cmp     eax, 80040155h
0x18001fccc  jnz     short loc_18001FD06
0x18001fcce  xor     ecx, ecx; pvReserved
0x18001fcd0  call    cs:__imp_CoInitialize
0x18001fcd6  test    eax, eax
0x18001fcd8  js      short loc_18001FD06
0x18001fcda  mov     ecx, 1
0x18001fcdf  lea     rax, [rbp+var_10]
0x18001fce3  mov     r13d, ecx
0x18001fce6  mov     [rsp+50h+ppv], rax; ppv
0x18001fceb  mov     r8d, ecx; dwClsContext
0x18001fcee  lea     r9, IID_IUniformResourceLocatorW; riid
0x18001fcf5  lea     rcx, CLSID_InternetShortcut; rclsid
0x18001fcfc  xor     edx, edx; pUnkOuter
0x18001fcfe  call    cs:__imp_CoCreateInstance
0x18001fd04  mov     ebx, eax
0x18001fd06  test    ebx, ebx
0x18001fd08  js      loc_18001FD95
0x18001fd0e  mov     rcx, [rbp+var_10]
0x18001fd12  mov     r8d, 1
0x18001fd18  mov     rdx, [rdi+18h]
0x18001fd1c  add     rdx, 22Ch
0x18001fd23  mov     rax, [rcx]
0x18001fd26  mov     rax, [rax+18h]
0x18001fd2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fd2f  mov     ebx, eax
0x18001fd31  test    eax, eax
0x18001fd33  js      short loc_18001FD85
0x18001fd35  mov     rcx, [rbp+var_10]
0x18001fd39  lea     r8, [rbp+var_8]
0x18001fd3d  lea     rdx, IID_IExtractIconW
0x18001fd44  mov     rax, [rcx]
0x18001fd47  mov     rax, [rax]
0x18001fd4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fd4f  mov     ebx, eax
0x18001fd51  test    eax, eax
0x18001fd53  js      short loc_18001FD85
0x18001fd55  mov     rcx, [rbp+var_8]
0x18001fd59  mov     r9d, r12d
0x18001fd5c  mov     edx, [rbp+arg_8]
0x18001fd5f  mov     r8, rsi
0x18001fd62  mov     [rsp+50h+var_28], r15
0x18001fd67  mov     [rsp+50h+ppv], r14
0x18001fd6c  mov     rax, [rcx]
0x18001fd6f  mov     rax, [rax+18h]
0x18001fd73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fd78  mov     ebx, eax
0x18001fd7a  mov     rax, [rbp+var_8]
0x18001fd7e  mov     [rdi+108h], rax
0x18001fd85  mov     rcx, [rbp+var_10]
0x18001fd89  mov     rax, [rcx]
0x18001fd8c  mov     rax, [rax+10h]
0x18001fd90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fd95  test    r13d, r13d
0x18001fd98  jz      short loc_18001FDA0
0x18001fd9a  call    cs:__imp_CoUninitialize
0x18001fda0  mov     eax, ebx
0x18001fda2  jmp     short loc_18001FDA9
0x18001fda4  mov     eax, 80070057h
0x18001fda9  mov     rbx, [rsp+50h+arg_0]
0x18001fdb1  add     rsp, 50h
0x18001fdb5  pop     r15
0x18001fdb7  pop     r14
0x18001fdb9  pop     r13
0x18001fdbb  pop     r12
0x18001fdbd  pop     rdi
0x18001fdbe  pop     rsi
0x18001fdbf  pop     rbp
0x18001fdc0  retn
```
