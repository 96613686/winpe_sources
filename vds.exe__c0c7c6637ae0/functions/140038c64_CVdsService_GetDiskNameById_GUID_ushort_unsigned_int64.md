# CVdsService::GetDiskNameById(_GUID *,ushort * *,unsigned __int64 &)

- ea: `0x140038c64`
- end: `0x140038f88`
- name: `?GetDiskNameById@CVdsService@@AEAAJPEAU_GUID@@PEAPEAGAEA_K@Z`
- size: `804`
- prototype: `int(CVdsService *__hidden this, struct _GUID *, unsigned __int16 **, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x140022400`

## callees

- `0x140006e60`
- `0x14000d6e0`
- `0x14000dd3c`
- `0x140023f58`
- `0x14002e123`
- `0x140038c64`
- `0x140052e46`
- `0x140052e80`
- `0x140056010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140038ea7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140038eba`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140038ecd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140038ee0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140038ef3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140038ea7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140038eba`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140038ecd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140038ee0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140038ef3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140038e24`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140038e24`
- `vdsutil!VdsHeapAlloc` at `0x140038e35`
- `vdsutil!VdsHeapAlloc` at `0x140038e35`
- `vdsutil!VdsTraceW` at `0x140038cc2`
- `vdsutil!VdsTraceW` at `0x140038e51`
- `vdsutil!VdsTraceW` at `0x140038e98`
- `vdsutil!VdsTraceW` at `0x140038f42`
- `vdsutil!VdsTraceW` at `0x140038f5f`
- `vdsutil!VdsTraceW` at `0x140038cc2`
- `vdsutil!VdsTraceW` at `0x140038e51`
- `vdsutil!VdsTraceW` at `0x140038e98`
- `vdsutil!VdsTraceW` at `0x140038f42`
- `vdsutil!VdsTraceW` at `0x140038f5f`

## string_xrefs

- `0x140038cb5`: `CVdsService::GetDiskNameById`
- `0x140038f56`: `CVdsService::GetDiskNameById, 1, pDiskId=%p, ppName=%p, nRet=%ld`
- `0x140038d3e`: `CVdsService::GetDiskNameById, 2, hr=%lX`
- `0x140038d6e`: `CVdsService::GetDiskNameById, 3, hr=%lX`
- `0x140038d89`: `CVdsService::GetDiskNameById, 4, hr=%lX`
- `0x140038db5`: `CVdsService::GetDiskNameById, 5, %lX`
- `0x140038ded`: `CVdsService::GetDiskNameById, 6, %lX`
- `0x140038e8c`: `CVdsService::GetDiskNameById, 7, %lX`
- `0x140038e43`: `CVdsService::GetDiskNameById, 8`
- `0x140038f36`: `EXIT CVdsService::GetDiskNameById, hr=%lX`

## pseudocode

```c
__int64 __fastcall CVdsService::GetDiskNameById(
        CVdsService *this,
        struct _GUID *a2,
        unsigned __int16 **a3,
        unsigned __int64 *a4)
{
  int v7; // edi
  int v8; // eax
  CVdsService *v9; // rcx
  int NameByIdForRaw; // eax
  unsigned int v11; // edi
  int ObjectFromProviders; // eax
  const wchar_t *v13; // rdx
  int v14; // eax
  int v15; // eax
  unsigned __int64 v16; // rsi
  __int64 v17; // rbx
  HANDLE ProcessHeap; // rax
  unsigned __int16 *v19; // rax
  __int64 v20; // rdx
  struct IUnknown *v22; // [rsp+30h] [rbp-89h] BYREF
  __int64 v23; // [rsp+38h] [rbp-81h] BYREF
  struct _GUID v24; // [rsp+40h] [rbp-79h] BYREF
  _BYTE v25[88]; // [rsp+50h] [rbp-69h] BYREF
  LPVOID v26; // [rsp+A8h] [rbp-11h]
  LPVOID pv; // [rsp+B0h] [rbp-9h]
  LPVOID v28; // [rsp+B8h] [rbp-1h]
  LPVOID v29; // [rsp+C0h] [rbp+7h]
  LPVOID v30; // [rsp+C8h] [rbp+Fh]

  v22 = 0;
  v23 = 0;
  v7 = 0;
  memset_0(v25, 0, 0x80u);
  *a4 = 0;
  VdsTraceW(2, L"CVdsService::GetDiskNameById");
  memset_0(v25, 0, 0x80u);
  if ( !a2 || (v8 = memcmp_0(&GUID_NULL, a2, 0x10u), v7 = v8, !a3) || !v8 )
  {
    VdsTraceW(0, L"CVdsService::GetDiskNameById, 1, pDiskId=%p, ppName=%p, nRet=%ld", a2, a3, v7);
    return 2147942487LL;
  }
  *a3 = 0;
  v24 = *a2;
  if ( (int)CVdsService::GetDisk(&v24, &v22) >= 0 )
  {
    NameByIdForRaw = CVdsService::GetNameByIdForRaw(v9, a2, a3, a4);
    v11 = NameByIdForRaw;
    if ( NameByIdForRaw < 0 )
      VdsTraceW(0, L"CVdsService::GetDiskNameById, 2, hr=%lX", (unsigned int)NameByIdForRaw);
    goto LABEL_28;
  }
  v24 = *a2;
  ObjectFromProviders = CVdsService::GetObjectFromProviders(&v24, VDS_OT_DISK, &v22);
  v11 = ObjectFromProviders;
  if ( ObjectFromProviders >= 0 )
  {
    if ( v22 )
    {
      v14 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, __int64 *))v22->lpVtbl->QueryInterface)(
              v22,
              &IID_IVdsDisk,
              &v23);
      v11 = v14;
      if ( v14 < 0 )
      {
        VdsTraceW(0, L"CVdsService::GetDiskNameById, 5, %lX", (unsigned int)v14);
        goto LABEL_28;
      }
      memset_0(v25, 0, 0x80u);
      v15 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v23 + 24LL))(v23, v25);
      v11 = v15;
      if ( v15 < 0 )
      {
        VdsTraceW(0, L"CVdsService::GetDiskNameById, 6, %lX", (unsigned int)v15);
        goto LABEL_28;
      }
      if ( pv )
      {
        v16 = -1;
        v17 = -1;
        do
          ++v17;
        while ( *((_WORD *)pv + v17) );
        if ( v17 )
        {
          ProcessHeap = GetProcessHeap();
          v19 = (unsigned __int16 *)VdsHeapAlloc(ProcessHeap, 8, 2 * v17 + 2);
          *a3 = v19;
          if ( v19 )
          {
            v20 = -1;
            do
              ++v20;
            while ( *((_WORD *)pv + v20) );
            StringCchCopyW(v19, v20 + 1, (const unsigned __int16 *)pv);
            do
              ++v16;
            while ( (*a3)[v16] );
            *a4 = v16;
          }
          else
          {
            v11 = -2147024882;
            VdsTraceW(0, L"CVdsService::GetDiskNameById, 8");
          }
          goto LABEL_28;
        }
      }
      v11 = -2147211505;
      v13 = L"CVdsService::GetDiskNameById, 7, %lX";
    }
    else
    {
      v11 = -2147212283;
      v13 = L"CVdsService::GetDiskNameById, 4, hr=%lX";
    }
    VdsTraceW(0, v13, v11);
    goto LABEL_28;
  }
  VdsTraceW(0, L"CVdsService::GetDiskNameById, 3, hr=%lX", (unsigned int)ObjectFromProviders);
LABEL_28:
  if ( pv )
  {
    CoTaskMemFree(pv);
    pv = 0;
  }
  if ( v26 )
  {
    CoTaskMemFree(v26);
    v26 = 0;
  }
  if ( v28 )
  {
    CoTaskMemFree(v28);
    v28 = 0;
  }
  if ( v29 )
  {
    CoTaskMemFree(v29);
    v29 = 0;
  }
  if ( v30 )
  {
    CoTaskMemFree(v30);
    v30 = 0;
  }
  if ( v22 )
  {
    ((void (__fastcall *)(struct IUnknown *))v22->lpVtbl->Release)(v22);
    v22 = 0;
  }
  if ( v23 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
    v23 = 0;
  }
  VdsTraceW(2, L"EXIT CVdsService::GetDiskNameById, hr=%lX", v11);
  return v11;
}

```

## disassembly

```asm
0x140038c64  push    rbp
0x140038c66  push    rbx
0x140038c67  push    rsi
0x140038c68  push    rdi
0x140038c69  push    r12
0x140038c6b  push    r14
0x140038c6d  push    r15
0x140038c6f  lea     rbp, [rsp-27h]
0x140038c74  sub     rsp, 0E0h
0x140038c7b  mov     rax, cs:__security_cookie
0x140038c82  xor     rax, rsp
0x140038c85  mov     [rbp+57h+var_40], rax
0x140038c89  xor     r12d, r12d
0x140038c8c  lea     rcx, [rbp+57h+var_C0]; void *
0x140038c90  mov     r14, r8
0x140038c93  mov     [rsp+110h+var_E0], r12
0x140038c98  mov     rbx, rdx
0x140038c9b  mov     [rsp+110h+var_D8], r12
0x140038ca0  mov     esi, 80h
0x140038ca5  xor     edx, edx; Val
0x140038ca7  mov     r8d, esi; Size
0x140038caa  mov     r15, r9
0x140038cad  mov     edi, r12d
0x140038cb0  call    memset_0
0x140038cb5  lea     rdx, aCvdsserviceGet_124; "CVdsService::GetDiskNameById"
0x140038cbc  mov     [r15], r12
0x140038cbf  lea     ecx, [rsi-7Eh]
0x140038cc2  call    cs:__imp_VdsTraceW
0x140038cc8  mov     r8d, esi; Size
0x140038ccb  lea     rcx, [rbp+57h+var_C0]; void *
0x140038ccf  xor     edx, edx; Val
0x140038cd1  call    memset_0
0x140038cd6  test    rbx, rbx
0x140038cd9  jz      loc_140038F4C
0x140038cdf  lea     r8d, [r12+10h]; Size
0x140038ce4  mov     rdx, rbx; Buf2
0x140038ce7  lea     rcx, GUID_NULL; Buf1
0x140038cee  call    memcmp_0
0x140038cf3  mov     edi, eax
0x140038cf5  test    r14, r14
0x140038cf8  jz      loc_140038F4C
0x140038cfe  test    eax, eax
0x140038d00  jz      loc_140038F4C
0x140038d06  mov     [r14], r12
0x140038d09  lea     rdx, [rsp+110h+var_E0]; struct IUnknown **
0x140038d0e  movups  xmm0, xmmword ptr [rbx]
0x140038d11  lea     rcx, [rbp+57h+var_D0]; struct _GUID
0x140038d15  movdqu  xmmword ptr [rbp+57h+var_D0.Data1], xmm0
0x140038d1a  call    ?GetDisk@CVdsService@@SAJU_GUID@@PEAPEAUIUnknown@@@Z; CVdsService::GetDisk(_GUID,IUnknown * *)
0x140038d1f  test    eax, eax
0x140038d21  js      short loc_140038D4A
0x140038d23  mov     r9, r15; unsigned __int64 *
0x140038d26  mov     r8, r14; unsigned __int16 **
0x140038d29  mov     rdx, rbx; struct _GUID *
0x140038d2c  call    ?GetNameByIdForRaw@CVdsService@@AEAAJPEAU_GUID@@PEAPEAGAEA_K@Z; CVdsService::GetNameByIdForRaw(_GUID *,ushort * *,unsigned __int64 &)
0x140038d31  mov     edi, eax
0x140038d33  test    eax, eax
0x140038d35  jns     loc_140038E9E
0x140038d3b  mov     r8d, eax
0x140038d3e  lea     rdx, aCvdsserviceGet_106; "CVdsService::GetDiskNameById, 2, hr=%lX"
0x140038d45  jmp     loc_140038E96
0x140038d4a  movups  xmm0, xmmword ptr [rbx]
0x140038d4d  lea     r8, [rsp+110h+var_E0]; struct IUnknown **
0x140038d52  mov     edx, 0Dh; enum _VDS_OBJECT_TYPE
0x140038d57  lea     rcx, [rbp+57h+var_D0]; struct _GUID
0x140038d5b  movdqu  xmmword ptr [rbp+57h+var_D0.Data1], xmm0
0x140038d60  call    ?GetObjectFromProviders@CVdsService@@SAJU_GUID@@W4_VDS_OBJECT_TYPE@@PEAPEAUIUnknown@@@Z; CVdsService::GetObjectFromProviders(_GUID,_VDS_OBJECT_TYPE,IUnknown * *)
0x140038d65  mov     edi, eax
0x140038d67  test    eax, eax
0x140038d69  jns     short loc_140038D7A
0x140038d6b  mov     r8d, eax
0x140038d6e  lea     rdx, aCvdsserviceGet_96; "CVdsService::GetDiskNameById, 3, hr=%lX"
0x140038d75  jmp     loc_140038E96
0x140038d7a  mov     rcx, [rsp+110h+var_E0]
0x140038d7f  test    rcx, rcx
0x140038d82  jnz     short loc_140038D95
0x140038d84  mov     edi, 80042405h
0x140038d89  lea     rdx, aCvdsserviceGet_123; "CVdsService::GetDiskNameById, 4, hr=%lX"
0x140038d90  jmp     loc_140038E93
0x140038d95  mov     rax, [rcx]
0x140038d98  lea     r8, [rsp+110h+var_D8]
0x140038d9d  lea     rdx, IID_IVdsDisk
0x140038da4  mov     rax, [rax]
0x140038da7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140038dac  mov     edi, eax
0x140038dae  test    eax, eax
0x140038db0  jns     short loc_140038DC1
0x140038db2  mov     r8d, eax
0x140038db5  lea     rdx, aCvdsserviceGet_18; "CVdsService::GetDiskNameById, 5, %lX"
0x140038dbc  jmp     loc_140038E96
0x140038dc1  mov     r8, rsi; Size
0x140038dc4  lea     rcx, [rbp+57h+var_C0]; void *
0x140038dc8  xor     edx, edx; Val
0x140038dca  call    memset_0
0x140038dcf  mov     rcx, [rsp+110h+var_D8]
0x140038dd4  lea     rdx, [rbp+57h+var_C0]
0x140038dd8  mov     rax, [rcx]
0x140038ddb  mov     rax, [rax+18h]
0x140038ddf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140038de4  mov     edi, eax
0x140038de6  test    eax, eax
0x140038de8  jns     short loc_140038DF9
0x140038dea  mov     r8d, eax
0x140038ded  lea     rdx, aCvdsserviceGet_108; "CVdsService::GetDiskNameById, 6, %lX"
0x140038df4  jmp     loc_140038E96
0x140038df9  mov     rax, [rbp+57h+pv]
0x140038dfd  test    rax, rax
0x140038e00  jz      loc_140038E87
0x140038e06  or      rsi, 0FFFFFFFFFFFFFFFFh
0x140038e0a  mov     rbx, rsi
0x140038e0d  inc     rbx
0x140038e10  cmp     [rax+rbx*2], r12w
0x140038e15  jnz     short loc_140038E0D
0x140038e17  test    rbx, rbx
0x140038e1a  jz      short loc_140038E87
0x140038e1c  lea     rbx, ds:2[rbx*2]
0x140038e24  call    cs:__imp_GetProcessHeap
0x140038e2a  mov     r8, rbx
0x140038e2d  mov     edx, 8
0x140038e32  mov     rcx, rax
0x140038e35  call    cs:__imp_VdsHeapAlloc
0x140038e3b  mov     [r14], rax
0x140038e3e  test    rax, rax
0x140038e41  jnz     short loc_140038E59
0x140038e43  lea     rdx, aCvdsserviceGet_134; "CVdsService::GetDiskNameById, 8"
0x140038e4a  xor     ecx, ecx
0x140038e4c  mov     edi, 8007000Eh
0x140038e51  call    cs:__imp_VdsTraceW
0x140038e57  jmp     short loc_140038E9E
0x140038e59  mov     r8, [rbp+57h+pv]; unsigned __int16 *
0x140038e5d  mov     rdx, rsi
0x140038e60  inc     rdx
0x140038e63  cmp     [r8+rdx*2], r12w
0x140038e68  jnz     short loc_140038E60
0x140038e6a  inc     rdx; unsigned __int64
0x140038e6d  mov     rcx, rax; unsigned __int16 *
0x140038e70  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x140038e75  mov     r10, [r14]
0x140038e78  inc     rsi
0x140038e7b  cmp     [r10+rsi*2], r12w
0x140038e80  jnz     short loc_140038E78
0x140038e82  mov     [r15], rsi
0x140038e85  jmp     short loc_140038E9E
0x140038e87  mov     edi, 8004270Fh
0x140038e8c  lea     rdx, aCvdsserviceGet_104; "CVdsService::GetDiskNameById, 7, %lX"
0x140038e93  mov     r8d, edi
0x140038e96  xor     ecx, ecx
0x140038e98  call    cs:__imp_VdsTraceW
0x140038e9e  mov     rcx, [rbp+57h+pv]; pv
0x140038ea2  test    rcx, rcx
0x140038ea5  jz      short loc_140038EB1
0x140038ea7  call    cs:__imp_CoTaskMemFree
0x140038ead  mov     [rbp+57h+pv], r12
0x140038eb1  mov     rcx, [rbp+57h+var_68]; pv
0x140038eb5  test    rcx, rcx
0x140038eb8  jz      short loc_140038EC4
0x140038eba  call    cs:__imp_CoTaskMemFree
0x140038ec0  mov     [rbp+57h+var_68], r12
0x140038ec4  mov     rcx, [rbp+57h+var_58]; pv
0x140038ec8  test    rcx, rcx
0x140038ecb  jz      short loc_140038ED7
0x140038ecd  call    cs:__imp_CoTaskMemFree
0x140038ed3  mov     [rbp+57h+var_58], r12
0x140038ed7  mov     rcx, [rbp+57h+var_50]; pv
0x140038edb  test    rcx, rcx
0x140038ede  jz      short loc_140038EEA
0x140038ee0  call    cs:__imp_CoTaskMemFree
0x140038ee6  mov     [rbp+57h+var_50], r12
0x140038eea  mov     rcx, [rbp+57h+var_48]; pv
0x140038eee  test    rcx, rcx
0x140038ef1  jz      short loc_140038EFD
0x140038ef3  call    cs:__imp_CoTaskMemFree
0x140038ef9  mov     [rbp+57h+var_48], r12
0x140038efd  mov     rcx, [rsp+110h+var_E0]
0x140038f02  test    rcx, rcx
0x140038f05  jz      short loc_140038F18
0x140038f07  mov     rax, [rcx]
0x140038f0a  mov     rax, [rax+10h]
0x140038f0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140038f13  mov     [rsp+110h+var_E0], r12
0x140038f18  mov     rcx, [rsp+110h+var_D8]
0x140038f1d  test    rcx, rcx
0x140038f20  jz      short loc_140038F33
0x140038f22  mov     rax, [rcx]
0x140038f25  mov     rax, [rax+10h]
0x140038f29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140038f2e  mov     [rsp+110h+var_D8], r12
0x140038f33  mov     r8d, edi
0x140038f36  lea     rdx, aExitCvdsservic_9; "EXIT CVdsService::GetDiskNameById, hr=%"...
0x140038f3d  mov     ecx, 2
0x140038f42  call    cs:__imp_VdsTraceW
0x140038f48  mov     eax, edi
0x140038f4a  jmp     short loc_140038F6A
0x140038f4c  mov     r9, r14
0x140038f4f  mov     [rsp+110h+var_F0], edi
0x140038f53  mov     r8, rbx
0x140038f56  lea     rdx, aCvdsserviceGet_128; "CVdsService::GetDiskNameById, 1, pDiskI"...
0x140038f5d  xor     ecx, ecx
0x140038f5f  call    cs:__imp_VdsTraceW
0x140038f65  mov     eax, 80070057h
0x140038f6a  mov     rcx, [rbp+57h+var_40]
0x140038f6e  xor     rcx, rsp; StackCookie
0x140038f71  call    __security_check_cookie
0x140038f76  add     rsp, 0E0h
0x140038f7d  pop     r15
0x140038f7f  pop     r14
0x140038f81  pop     r12
0x140038f83  pop     rdi
0x140038f84  pop     rsi
0x140038f85  pop     rbx
0x140038f86  pop     rbp
0x140038f87  retn
```
