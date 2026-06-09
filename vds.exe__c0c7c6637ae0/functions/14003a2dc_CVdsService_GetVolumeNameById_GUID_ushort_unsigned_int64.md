# CVdsService::GetVolumeNameById(_GUID,ushort * *,unsigned __int64 &)

- ea: `0x14003a2dc`
- end: `0x14003a587`
- name: `?GetVolumeNameById@CVdsService@@SAJU_GUID@@PEAPEAGAEA_K@Z`
- size: `683`
- prototype: `__int64 __fastcall(struct _GUID *__struct_ptr, unsigned __int16 **, unsigned __int64 *)`
- caller_count: `3`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x140022400`
- `0x140028768`
- `0x140029cf4`

## callees

- `0x140006e60`
- `0x14000dd3c`
- `0x14003a2dc`
- `0x140052e46`
- `0x140052e80`
- `0x140056010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14003a4ea`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14003a4ea`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14003a463`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14003a463`
- `vdsutil!VdsHeapAlloc` at `0x14003a474`
- `vdsutil!VdsHeapAlloc` at `0x14003a474`
- `vdsutil!VdsTraceW` at `0x14003a345`
- `vdsutil!VdsTraceW` at `0x14003a3b4`
- `vdsutil!VdsTraceW` at `0x14003a490`
- `vdsutil!VdsTraceW` at `0x14003a4db`
- `vdsutil!VdsTraceW` at `0x14003a530`
- `vdsutil!VdsTraceW` at `0x14003a553`
- `vdsutil!VdsTraceW` at `0x14003a345`
- `vdsutil!VdsTraceW` at `0x14003a3b4`
- `vdsutil!VdsTraceW` at `0x14003a490`
- `vdsutil!VdsTraceW` at `0x14003a4db`
- `vdsutil!VdsTraceW` at `0x14003a530`
- `vdsutil!VdsTraceW` at `0x14003a553`

## string_xrefs

- `0x14003a325`: `CVdsService::GetVolumeNameById`
- `0x14003a547`: `CVdsService::GetVolumeNameById, 1, hr=%lX, nRet=%ld, ppName=%p`
- `0x14003a3a8`: `CVdsService::GetVolumeNameById, 2, hr=%lX`
- `0x14003a3c9`: `CVdsService::GetVolumeNameById, 2b, hr=%lX`
- `0x14003a3f4`: `CVdsService::GetVolumeNameById, 3, %lX`
- `0x14003a42c`: `CVdsService::GetVolumeNameById, 4, %lX`
- `0x14003a4cc`: `CVdsService::GetVolumeNameById, 5, %lX`
- `0x14003a482`: `CVdsService::GetVolumeNameById, 6`
- `0x14003a524`: `EXIT CVdsService::GetVolumeNameById, hr=%lX`

## pseudocode

```c
__int64 __fastcall CVdsService::GetVolumeNameById(struct _GUID *a1, unsigned __int16 **a2, unsigned __int64 *a3)
{
  struct _GUID v3; // xmm6
  unsigned int v6; // eax
  int ObjectFromProviders; // eax
  struct IUnknown *v8; // r14
  unsigned int v9; // edi
  const wchar_t *v10; // rdx
  unsigned __int64 v11; // rsi
  __int64 v12; // rbx
  HANDLE ProcessHeap; // rax
  unsigned __int16 *v14; // rax
  __int64 v15; // rdx
  __int64 v17; // [rsp+38h] [rbp-49h] BYREF
  struct IUnknown *v18; // [rsp+40h] [rbp-41h] BYREF
  struct _GUID Buf2; // [rsp+48h] [rbp-39h] BYREF
  __int128 v20; // [rsp+58h] [rbp-29h] BYREF
  __int128 v21; // [rsp+68h] [rbp-19h]
  __int128 v22; // [rsp+78h] [rbp-9h]
  LPVOID pv; // [rsp+88h] [rbp+7h]

  v3 = *a1;
  Buf2 = *a1;
  pv = 0;
  v18 = 0;
  v17 = 0;
  *a3 = 0;
  v22 = 0;
  VdsTraceW(2, L"CVdsService::GetVolumeNameById");
  pv = 0;
  v20 = 0;
  v21 = 0;
  v22 = 0;
  v6 = memcmp_0(&GUID_NULL, &Buf2, 0x10u);
  if ( !v6 || !a2 )
  {
    VdsTraceW(0, L"CVdsService::GetVolumeNameById, 1, hr=%lX, nRet=%ld, ppName=%p", 2147942487LL, v6, a2);
    return 2147942487LL;
  }
  *a2 = 0;
  Buf2 = v3;
  ObjectFromProviders = CVdsService::GetObjectFromProviders(&Buf2, VDS_OT_VOLUME, &v18);
  v8 = v18;
  v9 = ObjectFromProviders;
  if ( ObjectFromProviders < 0 )
  {
    v10 = L"CVdsService::GetVolumeNameById, 2, hr=%lX";
LABEL_5:
    VdsTraceW(0, v10, (unsigned int)ObjectFromProviders);
    goto LABEL_25;
  }
  if ( v18 )
  {
    ObjectFromProviders = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, __int64 *))v18->lpVtbl->QueryInterface)(
                            v18,
                            &IID_IVdsVolume,
                            &v17);
    v9 = ObjectFromProviders;
    if ( ObjectFromProviders >= 0 )
    {
      pv = 0;
      v20 = 0;
      v21 = 0;
      v22 = 0;
      ObjectFromProviders = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v17 + 24LL))(v17, &v20);
      v9 = ObjectFromProviders;
      if ( ObjectFromProviders >= 0 )
      {
        if ( !pv )
          goto LABEL_24;
        v11 = -1;
        v12 = -1;
        do
          ++v12;
        while ( *((_WORD *)pv + v12) );
        if ( v12 )
        {
          ProcessHeap = GetProcessHeap();
          v14 = (unsigned __int16 *)VdsHeapAlloc(ProcessHeap, 8, 2 * v12 + 2);
          *a2 = v14;
          if ( v14 )
          {
            v15 = -1;
            do
              ++v15;
            while ( *((_WORD *)pv + v15) );
            StringCchCopyW(v14, v15 + 1, (const unsigned __int16 *)pv);
            do
              ++v11;
            while ( (*a2)[v11] );
            *a3 = v11;
          }
          else
          {
            v9 = -2147024882;
            VdsTraceW(0, L"CVdsService::GetVolumeNameById, 6");
          }
        }
        else
        {
LABEL_24:
          v9 = -2147211503;
          VdsTraceW(1, L"CVdsService::GetVolumeNameById, 5, %lX", 2147755793LL);
        }
        goto LABEL_25;
      }
      v10 = L"CVdsService::GetVolumeNameById, 4, %lX";
    }
    else
    {
      v10 = L"CVdsService::GetVolumeNameById, 3, %lX";
    }
    goto LABEL_5;
  }
  v9 = -2147212283;
  VdsTraceW(0, L"CVdsService::GetVolumeNameById, 2b, hr=%lX", 2147755013LL);
LABEL_25:
  if ( pv )
  {
    CoTaskMemFree(pv);
    pv = 0;
  }
  if ( v8 )
    ((void (__fastcall *)(struct IUnknown *))v8->lpVtbl->Release)(v8);
  if ( v17 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
    v17 = 0;
  }
  VdsTraceW(2, L"EXIT CVdsService::GetVolumeNameById, hr=%lX", v9);
  return v9;
}

```

## disassembly

```asm
0x14003a2dc  mov     rax, rsp
0x14003a2df  mov     [rax+20h], rbx
0x14003a2e3  push    rbp
0x14003a2e4  push    rsi
0x14003a2e5  push    rdi
0x14003a2e6  push    r12
0x14003a2e8  push    r13
0x14003a2ea  push    r14
0x14003a2ec  push    r15
0x14003a2ee  lea     rbp, [rax-5Fh]
0x14003a2f2  sub     rsp, 0A0h
0x14003a2f9  movaps  xmmword ptr [rax-48h], xmm6
0x14003a2fd  mov     rax, cs:__security_cookie
0x14003a304  xor     rax, rsp
0x14003a307  mov     [rbp+57h+var_48], rax
0x14003a30b  movaps  xmm6, xmmword ptr [rcx]
0x14003a30e  xorps   xmm0, xmm0
0x14003a311  xor     eax, eax
0x14003a313  movaps  [rbp+57h+Buf2], xmm6
0x14003a317  xor     r13d, r13d
0x14003a31a  mov     [rbp+57h+pv], rax
0x14003a31e  mov     r15, rdx
0x14003a321  mov     [rbp+57h+var_98], r13
0x14003a325  lea     rdx, aCvdsserviceGet_63; "CVdsService::GetVolumeNameById"
0x14003a32c  mov     [rbp+57h+var_A0], r13
0x14003a330  lea     ecx, [rax+2]
0x14003a333  mov     [r8], r13
0x14003a336  mov     r12, r8
0x14003a339  movups  [rbp+57h+var_80], xmm0
0x14003a33d  movups  [rbp+57h+var_70], xmm0
0x14003a341  movups  [rbp+57h+var_60], xmm0
0x14003a345  call    cs:__imp_VdsTraceW
0x14003a34b  xorps   xmm0, xmm0
0x14003a34e  lea     r8d, [r13+10h]; Size
0x14003a352  xor     eax, eax
0x14003a354  lea     rdx, [rbp+57h+Buf2]; Buf2
0x14003a358  lea     rcx, GUID_NULL; Buf1
0x14003a35f  mov     [rbp+57h+pv], rax
0x14003a363  movups  [rbp+57h+var_80], xmm0
0x14003a367  movups  [rbp+57h+var_70], xmm0
0x14003a36b  movups  [rbp+57h+var_60], xmm0
0x14003a36f  call    memcmp_0
0x14003a374  test    eax, eax
0x14003a376  jz      loc_14003A53A
0x14003a37c  test    r15, r15
0x14003a37f  jz      loc_14003A53A
0x14003a385  lea     r8, [rbp+57h+var_98]; struct IUnknown **
0x14003a389  mov     [r15], r13
0x14003a38c  lea     edx, [r13+0Bh]; enum _VDS_OBJECT_TYPE
0x14003a390  movdqa  [rbp+57h+Buf2], xmm6
0x14003a395  lea     rcx, [rbp+57h+Buf2]; struct _GUID
0x14003a399  call    ?GetObjectFromProviders@CVdsService@@SAJU_GUID@@W4_VDS_OBJECT_TYPE@@PEAPEAUIUnknown@@@Z; CVdsService::GetObjectFromProviders(_GUID,_VDS_OBJECT_TYPE,IUnknown * *)
0x14003a39e  mov     r14, [rbp+57h+var_98]
0x14003a3a2  mov     edi, eax
0x14003a3a4  test    eax, eax
0x14003a3a6  jns     short loc_14003A3BF
0x14003a3a8  lea     rdx, aCvdsserviceGet_56; "CVdsService::GetVolumeNameById, 2, hr=%"...
0x14003a3af  mov     r8d, eax
0x14003a3b2  xor     ecx, ecx
0x14003a3b4  call    cs:__imp_VdsTraceW
0x14003a3ba  jmp     loc_14003A4E1
0x14003a3bf  test    r14, r14
0x14003a3c2  jnz     short loc_14003A3D5
0x14003a3c4  mov     edi, 80042405h
0x14003a3c9  lea     rdx, aCvdsserviceGet_70; "CVdsService::GetVolumeNameById, 2b, hr="...
0x14003a3d0  mov     r8d, edi
0x14003a3d3  jmp     short loc_14003A3B2
0x14003a3d5  mov     rax, [r14]
0x14003a3d8  lea     r8, [rbp+57h+var_A0]
0x14003a3dc  lea     rdx, IID_IVdsVolume
0x14003a3e3  mov     rcx, r14
0x14003a3e6  mov     rax, [rax]
0x14003a3e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003a3ee  mov     edi, eax
0x14003a3f0  test    eax, eax
0x14003a3f2  jns     short loc_14003A3FD
0x14003a3f4  lea     rdx, aCvdsserviceGet_53; "CVdsService::GetVolumeNameById, 3, %lX"
0x14003a3fb  jmp     short loc_14003A3AF
0x14003a3fd  mov     rcx, [rbp+57h+var_A0]
0x14003a401  lea     rdx, [rbp+57h+var_80]
0x14003a405  xorps   xmm0, xmm0
0x14003a408  xor     eax, eax
0x14003a40a  mov     [rbp+57h+pv], rax
0x14003a40e  movups  [rbp+57h+var_80], xmm0
0x14003a412  movups  [rbp+57h+var_70], xmm0
0x14003a416  movups  [rbp+57h+var_60], xmm0
0x14003a41a  mov     rax, [rcx]
0x14003a41d  mov     rax, [rax+18h]
0x14003a421  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003a426  mov     edi, eax
0x14003a428  test    eax, eax
0x14003a42a  jns     short loc_14003A438
0x14003a42c  lea     rdx, aCvdsserviceGet_85; "CVdsService::GetVolumeNameById, 4, %lX"
0x14003a433  jmp     loc_14003A3AF
0x14003a438  mov     rax, [rbp+57h+pv]
0x14003a43c  test    rax, rax
0x14003a43f  jz      loc_14003A4C7
0x14003a445  or      rsi, 0FFFFFFFFFFFFFFFFh
0x14003a449  mov     rbx, rsi
0x14003a44c  inc     rbx
0x14003a44f  cmp     [rax+rbx*2], r13w
0x14003a454  jnz     short loc_14003A44C
0x14003a456  test    rbx, rbx
0x14003a459  jz      short loc_14003A4C7
0x14003a45b  lea     rbx, ds:2[rbx*2]
0x14003a463  call    cs:__imp_GetProcessHeap
0x14003a469  mov     r8, rbx
0x14003a46c  mov     edx, 8
0x14003a471  mov     rcx, rax
0x14003a474  call    cs:__imp_VdsHeapAlloc
0x14003a47a  mov     [r15], rax
0x14003a47d  test    rax, rax
0x14003a480  jnz     short loc_14003A498
0x14003a482  lea     rdx, aCvdsserviceGet_11; "CVdsService::GetVolumeNameById, 6"
0x14003a489  xor     ecx, ecx
0x14003a48b  mov     edi, 8007000Eh
0x14003a490  call    cs:__imp_VdsTraceW
0x14003a496  jmp     short loc_14003A4E1
0x14003a498  mov     r8, [rbp+57h+pv]; unsigned __int16 *
0x14003a49c  mov     rdx, rsi
0x14003a49f  inc     rdx
0x14003a4a2  cmp     [r8+rdx*2], r13w
0x14003a4a7  jnz     short loc_14003A49F
0x14003a4a9  inc     rdx; unsigned __int64
0x14003a4ac  mov     rcx, rax; unsigned __int16 *
0x14003a4af  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x14003a4b4  mov     r10, [r15]
0x14003a4b7  inc     rsi
0x14003a4ba  cmp     [r10+rsi*2], r13w
0x14003a4bf  jnz     short loc_14003A4B7
0x14003a4c1  mov     [r12], rsi
0x14003a4c5  jmp     short loc_14003A4E1
0x14003a4c7  mov     edi, 80042711h
0x14003a4cc  lea     rdx, aCvdsserviceGet_121; "CVdsService::GetVolumeNameById, 5, %lX"
0x14003a4d3  mov     r8d, edi
0x14003a4d6  mov     ecx, 1
0x14003a4db  call    cs:__imp_VdsTraceW
0x14003a4e1  mov     rcx, [rbp+57h+pv]; pv
0x14003a4e5  test    rcx, rcx
0x14003a4e8  jz      short loc_14003A4F4
0x14003a4ea  call    cs:__imp_CoTaskMemFree
0x14003a4f0  mov     [rbp+57h+pv], r13
0x14003a4f4  test    r14, r14
0x14003a4f7  jz      short loc_14003A508
0x14003a4f9  mov     rax, [r14]
0x14003a4fc  mov     rcx, r14
0x14003a4ff  mov     rax, [rax+10h]
0x14003a503  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003a508  mov     rcx, [rbp+57h+var_A0]
0x14003a50c  test    rcx, rcx
0x14003a50f  jz      short loc_14003A521
0x14003a511  mov     rax, [rcx]
0x14003a514  mov     rax, [rax+10h]
0x14003a518  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003a51d  mov     [rbp+57h+var_A0], r13
0x14003a521  mov     r8d, edi
0x14003a524  lea     rdx, aExitCvdsservic_12; "EXIT CVdsService::GetVolumeNameById, hr"...
0x14003a52b  mov     ecx, 2
0x14003a530  call    cs:__imp_VdsTraceW
0x14003a536  mov     eax, edi
0x14003a538  jmp     short loc_14003A55B
0x14003a53a  mov     ebx, 80070057h
0x14003a53f  mov     [rsp+0D0h+var_B0], r15
0x14003a544  mov     r8d, ebx
0x14003a547  lea     rdx, aCvdsserviceGet_72; "CVdsService::GetVolumeNameById, 1, hr=%"...
0x14003a54e  mov     r9d, eax
0x14003a551  xor     ecx, ecx
0x14003a553  call    cs:__imp_VdsTraceW
0x14003a559  mov     eax, ebx
0x14003a55b  mov     rcx, [rbp+57h+var_48]
0x14003a55f  xor     rcx, rsp; StackCookie
0x14003a562  call    __security_check_cookie
0x14003a567  lea     r11, [rsp+0D0h+var_30]
0x14003a56f  mov     rbx, [r11+58h]
0x14003a573  movaps  xmm6, xmmword ptr [r11-10h]
0x14003a578  mov     rsp, r11
0x14003a57b  pop     r15
0x14003a57d  pop     r14
0x14003a57f  pop     r13
0x14003a581  pop     r12
0x14003a583  pop     rdi
0x14003a584  pop     rsi
0x14003a585  pop     rbp
0x14003a586  retn
```
