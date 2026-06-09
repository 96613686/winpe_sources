# SxspComClassRedirectionGuidSectionGenerationCallback(void *,ulong,void *)

- ea: `0x18004a060`
- end: `0x18004a7b4`
- name: `?SxspComClassRedirectionGuidSectionGenerationCallback@@YAHPEAXK0@Z`
- size: `1876`
- prototype: `__int64 __fastcall(void *, unsigned int, void *)`
- caller_count: `0`
- callee_count: `13`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x18000a804`
- `0x18000dffc`
- `0x18001c2c8`
- `0x180022f60`
- `0x18004a060`
- `0x18004a7bc`
- `0x18004a810`
- `0x18004aac0`
- `0x18004ab60`
- `0x18004ac00`
- `0x180067548`
- `0x180067680`
- `0x18006a110`

## import_xrefs

- `ntdll!RtlPopFrame` at `0x18004a18a`
- `ntdll!RtlPopFrame` at `0x18004a18a`
- `ntdll!RtlPushFrame` at `0x18004a0ca`
- `ntdll!RtlPushFrame` at `0x18004a0ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a79a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a79a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004a304`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004a3c3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004a4a5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004a505`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004a562`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004a5c8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004a62b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004a654`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004a6f3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004a304`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004a3c3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004a4a5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004a505`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004a562`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004a5c8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004a62b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004a654`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004a6f3`

## pseudocode

```c
__int64 __fastcall SxspComClassRedirectionGuidSectionGenerationCallback(_QWORD *a1, int a2, __int64 *a3)
{
  int v6; // edi
  __int64 v7; // rcx
  __int64 v8; // rax
  __int64 v9; // rdx
  unsigned int v10; // ebx
  _QWORD *v12; // rdx
  __int64 v13; // rax
  __int64 v14; // r8
  _QWORD *i; // rcx
  int v16; // edi
  int v17; // edi
  __int64 v18; // rbx
  __int64 v19; // rcx
  unsigned __int64 v20; // rax
  __int64 v21; // rdi
  __int64 v22; // rsi
  __int128 v23; // xmm0
  int v24; // r15d
  int v25; // r12d
  __int64 v26; // rdx
  void *v27; // rdi
  __int64 v28; // r8
  __int64 v29; // rdx
  __int64 v30; // rax
  _QWORD **v31; // rsi
  _QWORD *j; // rdi
  DWORD LastError; // eax
  __int64 v34; // [rsp+48h] [rbp-39h] BYREF
  __int64 v35; // [rsp+50h] [rbp-31h] BYREF
  unsigned __int64 v36; // [rsp+58h] [rbp-29h] BYREF
  int v37; // [rsp+60h] [rbp-21h] BYREF
  struct _TEB_ACTIVE_FRAME Frame; // [rsp+68h] [rbp-19h] BYREF
  __int64 v39; // [rsp+80h] [rbp-1h]
  int v40; // [rsp+88h] [rbp+7h]
  int *v41; // [rsp+90h] [rbp+Fh]

  Frame.Context = (PCTEB_ACTIVE_FRAME_CONTEXT)&qword_1800718F0;
  v37 = 0;
  Frame.Previous = 0;
  v41 = &v37;
  Frame.Flags = 1;
  v39 = 544438355;
  v40 = 1161;
  RtlPushFrame(&Frame);
  if ( g_FusionEnterExitTracingEnabled )
    FusionpTraceCallEntry();
  if ( !a3 )
    goto LABEL_34;
  if ( a2 == 4 )
  {
    if ( a1 )
    {
      *a3 = 0;
      v12 = a1 + 21;
      v13 = a1[30];
      v14 = 0;
      if ( v13 )
      {
        v14 = 2 * v13 + 2;
        *a3 = v14;
      }
      for ( i = (_QWORD *)*v12; i && i != v12; i = (_QWORD *)*i )
      {
        v14 += 2LL * i[8] + 2;
        *a3 = v14;
      }
      goto LABEL_9;
    }
    goto LABEL_34;
  }
  v6 = a2 - 1;
  if ( !v6 )
  {
    v7 = *a3;
    v8 = 120;
    a3[1] = 120;
    v9 = *(_QWORD *)(v7 + 168);
    if ( v9 )
    {
      v8 = 2 * v9 + 122;
      a3[1] = v8;
    }
    if ( *(_QWORD *)(v7 + 392) )
    {
      v28 = v8 + 44;
      a3[1] = v8 + 44;
      v29 = *(_QWORD *)(v7 + 448);
      if ( v29 )
      {
        v28 = v8 + 2 * (v29 + 23);
        a3[1] = v28;
      }
      if ( !*(_BYTE *)(v7 + 476) )
      {
        v28 += 2LL * *(_QWORD *)(v7 + 392) + 2;
        a3[1] = v28;
      }
      v30 = *(_QWORD *)(v7 + 336);
      if ( v30 )
        a3[1] = v28 + 2 * (v30 + 1);
    }
    goto LABEL_9;
  }
  v16 = v6 - 1;
  if ( !v16 )
  {
    v20 = a3[2];
    v21 = a3[3];
    if ( v20 < 0x78 )
    {
      SetLastError(0x7Au);
      *v41 = 0;
      FusionpTraceWin32LastErrorFailureOrigination((const struct _CALL_SITE_INFO *)off_18007AC70);
      goto LABEL_10;
    }
    v22 = a3[1];
    v36 = v20 - 120;
    *(_DWORD *)v21 = 120;
    v34 = 120;
    *(_DWORD *)(v21 + 4) = *(_DWORD *)(v22 + 108);
    *(_DWORD *)(v21 + 8) = *(_DWORD *)(v22 + 104);
    v23 = *(_OWORD *)(v22 + 40);
    v35 = v21 + 120;
    *(_OWORD *)(v21 + 12) = v23;
    *(_OWORD *)(v21 + 28) = *(_OWORD *)(v22 + 56);
    *(_OWORD *)(v21 + 44) = *(_OWORD *)(v22 + 72);
    *(_OWORD *)(v21 + 60) = *(_OWORD *)(v22 + 88);
    *(_DWORD *)(v21 + 100) = *(_DWORD *)(v22 + 112);
    *(_DWORD *)(v21 + 112) = *(_DWORD *)(v22 + 116);
    *(_DWORD *)(v21 + 104) = *(_DWORD *)(v22 + 124);
    *(_DWORD *)(v21 + 116) = *(_DWORD *)(v22 + 120);
    *(_DWORD *)(v21 + 108) = *(_DWORD *)(v22 + 128);
    if ( *(_QWORD *)(v22 + 392) )
    {
      if ( v20 - 120 < 0x2C )
      {
        SetLastError(0x7Au);
        *v41 = 0;
        FusionpTraceWin32LastErrorFailureOrigination((const struct _CALL_SITE_INFO *)off_18007AC50);
        goto LABEL_10;
      }
      v34 = 164;
      v36 = v20 - 164;
      v35 = v21 + 164;
      SetLastError(0);
      if ( !(unsigned int)CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32CopyIntoBuffer(
                            (int)v22 + 304,
                            (unsigned int)&v35,
                            (unsigned int)&v36,
                            (unsigned int)&v34,
                            v21 + 120,
                            v21 + 144,
                            v21 + 140) )
      {
        *v41 = 0;
        FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)off_18007AC30);
        goto LABEL_10;
      }
      *(_DWORD *)(v21 + 132) = 2 * *(_DWORD *)(*(_QWORD *)(v22 + 32) + 64LL);
      *(_DWORD *)(v21 + 136) = *(_DWORD *)(*(_QWORD *)(v22 + 32) + 240LL);
      SetLastError(0);
      if ( !(unsigned int)CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32CopyIntoBuffer(
                            (int)v22 + 416,
                            (unsigned int)&v35,
                            (unsigned int)&v36,
                            (unsigned int)&v34,
                            v21 + 120,
                            v21 + 152,
                            v21 + 148) )
      {
        *v41 = 0;
        FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)off_180071A30);
        goto LABEL_10;
      }
      v25 = v34 - 120;
      if ( *(_BYTE *)(v22 + 476) )
      {
        *(_DWORD *)(v21 + 80) = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v22 + 32) + 248LL) + 264LL);
        *(_DWORD *)(v21 + 76) = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v22 + 32) + 248LL) + 268LL);
      }
      else
      {
        SetLastError(0);
        if ( !(unsigned int)CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32CopyIntoBuffer(
                              (int)v22 + 360,
                              (unsigned int)&v35,
                              (unsigned int)&v36,
                              (unsigned int)&v34,
                              *a3,
                              v21 + 80,
                              v21 + 76) )
        {
          *v41 = 0;
          FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)off_18007AC10);
          goto LABEL_10;
        }
      }
      *(_QWORD *)(v21 + 120) = 44;
      *(_DWORD *)(v21 + 128) = *(_DWORD *)(v22 + 472);
      *(_QWORD *)(v21 + 156) = 0;
      v24 = 120;
    }
    else
    {
      v24 = 0;
      v25 = 0;
      *(_DWORD *)(v21 + 76) = 2 * *(_DWORD *)(*(_QWORD *)(v22 + 32) + 64LL);
      *(_DWORD *)(v21 + 80) = *(_DWORD *)(*(_QWORD *)(v22 + 32) + 240LL);
    }
    *(_DWORD *)(v21 + 92) = v25;
    *(_DWORD *)(v21 + 96) = v24;
    SetLastError(0);
    if ( !(unsigned int)CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32CopyIntoBuffer(
                          (int)v22 + 136,
                          (unsigned int)&v35,
                          (unsigned int)&v36,
                          (unsigned int)&v34,
                          v21,
                          v21 + 88,
                          v21 + 84) )
    {
      *v41 = 0;
      FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)off_180071930);
      goto LABEL_10;
    }
    a3[4] = v34;
LABEL_9:
    v37 = 1;
    goto LABEL_10;
  }
  v17 = v16 - 1;
  if ( !v17 )
  {
    if ( a1 )
    {
      v18 = *a3;
      if ( v18 )
      {
        v19 = *(_QWORD *)(v18 + 32);
        if ( v19 )
        {
          CDeque<_COM_SERVER_ENTRY,0>::Remove((CDequeBase *)(v19 + 200), (struct CDequeLinkage *)v18);
          v26 = *(_QWORD *)(v18 + 32);
          if ( !*(_QWORD *)(v26 + 232) )
          {
            CDeque<_COM_FILE_CONTEXT,0>::Remove((CDequeBase *)(a1 + 21), (struct CDequeLinkage *)v26);
            v27 = *(void **)(v18 + 32);
            if ( v27 )
            {
              _COM_FILE_CONTEXT::~_COM_FILE_CONTEXT(*(_COM_FILE_CONTEXT **)(v18 + 32));
              operator delete(v27);
            }
            *(_QWORD *)(v18 + 32) = 0;
          }
        }
        _COM_SERVER_ENTRY::~_COM_SERVER_ENTRY((_COM_SERVER_ENTRY *)v18);
        operator delete((void *)v18);
      }
      goto LABEL_9;
    }
    goto LABEL_34;
  }
  if ( v17 != 2 )
    goto LABEL_9;
  if ( !a1 )
  {
LABEL_34:
    SetLastError(0x54Fu);
    *v41 = 0;
    goto LABEL_10;
  }
  v36 = a3[1];
  v34 = a3[2];
  v35 = 0;
  if ( !a1[30]
    || (SetLastError(0),
        (unsigned int)CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32CopyIntoBuffer(
                        (int)a1 + 208,
                        (unsigned int)&v34,
                        (unsigned int)&v36,
                        (unsigned int)&v35,
                        *a3,
                        (__int64)(a1 + 33),
                        (__int64)a1 + 268)) )
  {
    v31 = (_QWORD **)(a1 + 21);
    for ( j = *v31; ; j = (_QWORD *)*j )
    {
      if ( !j || j == v31 )
      {
        a3[3] = v35;
        goto LABEL_9;
      }
      SetLastError(0);
      if ( !(unsigned int)CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32CopyIntoBuffer(
                            (int)j + 32,
                            (unsigned int)&v34,
                            (unsigned int)&v36,
                            (unsigned int)&v35,
                            *a3,
                            (__int64)(j + 30),
                            0) )
        break;
    }
    *v41 = 0;
    FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)off_1800719F0);
  }
  else
  {
    *v41 = 0;
    FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)off_180071A50);
  }
LABEL_10:
  v10 = v37;
  if ( g_FusionEnterExitTracingEnabled )
  {
    if ( *v41 )
    {
      FusionpTraceCallSuccessfulExit(0);
    }
    else
    {
      LastError = GetLastError();
      FusionpTraceCallWin32UnsuccessfulExit(LastError, 0);
    }
  }
  RtlPopFrame(&Frame);
  return v10;
}

```

## disassembly

```asm
0x18004a060  mov     r11, rsp
0x18004a063  push    rbp
0x18004a064  push    rbx
0x18004a065  lea     rbp, [r11-5Fh]
0x18004a069  sub     rsp, 0C8h
0x18004a070  mov     rax, cs:__security_cookie
0x18004a077  xor     rax, rsp
0x18004a07a  mov     [rbp+57h+var_40], rax
0x18004a07e  mov     [r11+10h], rsi
0x18004a082  lea     rax, qword_1800718F0
0x18004a089  mov     [r11-18h], rdi
0x18004a08d  mov     rsi, rcx
0x18004a090  mov     [r11-28h], r13
0x18004a094  lea     rcx, [rbp+57h+Frame]; Frame
0x18004a098  mov     [rbp+57h+Frame.Context], rax
0x18004a09c  xor     r13d, r13d
0x18004a09f  lea     rax, [rbp+57h+var_78]
0x18004a0a3  mov     [rbp+57h+var_78], r13d
0x18004a0a7  mov     [rbp+57h+Frame.Previous], r13
0x18004a0ab  mov     rbx, r8
0x18004a0ae  mov     [rbp+57h+var_48], rax
0x18004a0b2  mov     edi, edx
0x18004a0b4  mov     [rbp+57h+Frame.Flags], 1
0x18004a0bb  mov     [rbp+57h+var_58], 20737853h
0x18004a0c3  mov     [rbp+57h+var_50], 489h
0x18004a0ca  call    cs:__imp_RtlPushFrame
0x18004a0d1  nop     dword ptr [rax+rax+00h]
0x18004a0d6  cmp     cs:g_FusionEnterExitTracingEnabled, r13b
0x18004a0dd  jnz     loc_18004A243
0x18004a0e3  mov     [rsp+0D0h+var_18], r12
0x18004a0eb  mov     [rsp+0D0h+var_28], r14
0x18004a0f3  mov     [rsp+0D0h+var_30], r15
0x18004a0fb  test    rbx, rbx
0x18004a0fe  jz      loc_18004A3BE
0x18004a104  cmp     edi, 4
0x18004a107  jz      loc_18004A1AF
0x18004a10d  sub     edi, 1
0x18004a110  jnz     loc_18004A1FE
0x18004a116  mov     rcx, [rbx]
0x18004a119  mov     eax, 78h ; 'x'
0x18004a11e  mov     [rbx+8], rax
0x18004a122  mov     rdx, [rcx+0A8h]
0x18004a129  test    rdx, rdx
0x18004a12c  jnz     loc_18004A3AD
0x18004a132  cmp     [rcx+188h], r13
0x18004a139  jnz     loc_18004A3DB
0x18004a13f  mov     [rbp+57h+var_78], 1
0x18004a146  cmp     cs:g_FusionEnterExitTracingEnabled, 0
0x18004a14d  mov     ebx, [rbp+57h+var_78]
0x18004a150  mov     r15, [rsp+0D0h+var_30]
0x18004a158  mov     r14, [rsp+0D0h+var_28]
0x18004a160  mov     r13, [rsp+0D0h+var_20]
0x18004a168  mov     r12, [rsp+0D0h+var_18]
0x18004a170  mov     rdi, [rsp+0C0h]
0x18004a178  mov     rsi, [rsp+0D0h+arg_8]
0x18004a180  jnz     loc_18004A785
0x18004a186  lea     rcx, [rbp+57h+Frame]; Frame
0x18004a18a  call    cs:__imp_RtlPopFrame
0x18004a191  nop     dword ptr [rax+rax+00h]
0x18004a196  mov     eax, ebx
0x18004a198  mov     rcx, [rbp+57h+var_40]
0x18004a19c  xor     rcx, rsp; StackCookie
0x18004a19f  call    __security_check_cookie
0x18004a1a4  add     rsp, 0C8h
0x18004a1ab  pop     rbx
0x18004a1ac  pop     rbp
0x18004a1ad  retn
0x18004a1af  test    rsi, rsi
0x18004a1b2  jz      loc_18004A3BE
0x18004a1b8  mov     [rbx], r13
0x18004a1bb  lea     rdx, [rsi+0A8h]
0x18004a1c2  mov     rax, [rsi+0F0h]
0x18004a1c9  mov     r8, r13
0x18004a1cc  test    rax, rax
0x18004a1cf  jnz     loc_18004A775
0x18004a1d5  mov     rcx, [rdx]
0x18004a1d8  test    rcx, rcx
0x18004a1db  jz      loc_18004A13F
0x18004a1e1  cmp     rcx, rdx
0x18004a1e4  jz      loc_18004A13F
0x18004a1ea  mov     rax, [rcx+40h]
0x18004a1ee  lea     r8, [r8+rax*2]
0x18004a1f2  add     r8, 2
0x18004a1f6  mov     [rbx], r8
0x18004a1f9  mov     rcx, [rcx]
0x18004a1fc  jmp     short loc_18004A1D8
0x18004a1fe  sub     edi, 1
0x18004a201  jz      short loc_18004A24D
0x18004a203  sub     edi, 1
0x18004a206  jnz     loc_18004A420
0x18004a20c  test    rsi, rsi
0x18004a20f  jz      loc_18004A3BE
0x18004a215  mov     rbx, [rbx]
0x18004a218  test    rbx, rbx
0x18004a21b  jz      loc_18004A13F
0x18004a221  mov     rcx, [rbx+20h]
0x18004a225  test    rcx, rcx
0x18004a228  jnz     loc_18004A35F
0x18004a22e  mov     rcx, rbx; this
0x18004a231  call    ??1_COM_SERVER_ENTRY@@QEAA@XZ; _COM_SERVER_ENTRY::~_COM_SERVER_ENTRY(void)
0x18004a236  mov     rcx, rbx; void *
0x18004a239  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18004a23e  jmp     loc_18004A13F
0x18004a243  call    ?FusionpTraceCallEntry@@YAXXZ; FusionpTraceCallEntry(void)
0x18004a248  jmp     loc_18004A0E3
0x18004a24d  mov     rax, [rbx+10h]
0x18004a251  mov     rdi, [rbx+18h]
0x18004a255  cmp     rax, 78h ; 'x'
0x18004a259  jb      loc_18004A626
0x18004a25f  mov     rsi, [rbx+8]
0x18004a263  lea     rcx, [rax-78h]
0x18004a267  mov     eax, 78h ; 'x'
0x18004a26c  mov     [rbp+57h+var_80], rcx
0x18004a270  mov     [rdi], eax
0x18004a272  lea     r15, [rdi+78h]
0x18004a276  mov     [rbp+57h+var_90], rax
0x18004a27a  mov     eax, [rsi+6Ch]
0x18004a27d  mov     [rdi+4], eax
0x18004a280  mov     eax, [rsi+68h]
0x18004a283  mov     [rdi+8], eax
0x18004a286  movups  xmm0, xmmword ptr [rsi+28h]
0x18004a28a  mov     [rbp+57h+var_88], r15
0x18004a28e  movups  xmmword ptr [rdi+0Ch], xmm0
0x18004a292  movups  xmm0, xmmword ptr [rsi+38h]
0x18004a296  movups  xmmword ptr [rdi+1Ch], xmm0
0x18004a29a  movups  xmm0, xmmword ptr [rsi+48h]
0x18004a29e  movups  xmmword ptr [rdi+2Ch], xmm0
0x18004a2a2  movups  xmm0, xmmword ptr [rsi+58h]
0x18004a2a6  movups  xmmword ptr [rdi+3Ch], xmm0
0x18004a2aa  mov     eax, [rsi+70h]
0x18004a2ad  mov     [rdi+64h], eax
0x18004a2b0  mov     eax, [rsi+74h]
0x18004a2b3  mov     [rdi+70h], eax
0x18004a2b6  mov     eax, [rsi+7Ch]
0x18004a2b9  mov     [rdi+68h], eax
0x18004a2bc  mov     eax, [rsi+78h]
0x18004a2bf  mov     [rdi+74h], eax
0x18004a2c2  mov     eax, [rsi+80h]
0x18004a2c8  mov     [rdi+6Ch], eax
0x18004a2cb  cmp     [rsi+188h], r13
0x18004a2d2  jnz     loc_18004A481
0x18004a2d8  mov     rax, [rsi+20h]
0x18004a2dc  mov     r15d, r13d
0x18004a2df  mov     r12d, r13d
0x18004a2e2  mov     ecx, [rax+40h]
0x18004a2e5  add     ecx, ecx
0x18004a2e7  mov     [rdi+4Ch], ecx
0x18004a2ea  mov     rax, [rsi+20h]
0x18004a2ee  mov     ecx, [rax+0F0h]
0x18004a2f4  mov     [rdi+50h], ecx
0x18004a2f7  mov     [rdi+5Ch], r12d
0x18004a2fb  xor     ecx, ecx; dwErrCode
0x18004a2fd  mov     [rdi+60h], r15d
0x18004a301  mov     r14, rdi
0x18004a304  call    cs:__imp_SetLastError
0x18004a30b  nop     dword ptr [rax+rax+00h]
0x18004a310  lea     rax, [rdi+54h]
0x18004a314  mov     [rsp+30h], rax
0x18004a319  lea     rdx, [rdi+58h]
0x18004a31d  mov     [rsp+0D0h+var_A8], rdx
0x18004a322  lea     rcx, [rsi+88h]
0x18004a329  lea     rdx, [rbp+57h+var_88]
0x18004a32d  mov     [rsp+0D0h+var_B0], rdi
0x18004a332  lea     r9, [rbp+57h+var_90]
0x18004a336  lea     r8, [rbp+57h+var_80]
0x18004a33a  call    ?Win32CopyIntoBuffer@?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@QEBAHPEAPEAGPEA_K1PEAXPEAK3@Z; CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32CopyIntoBuffer(ushort * *,unsigned __int64 *,unsigned __int64 *,void *,ulong *,ulong *)
0x18004a33f  test    eax, eax
0x18004a341  jnz     loc_18004A474
0x18004a347  mov     rax, [rbp+57h+var_48]
0x18004a34b  lea     rcx, off_180071930; struct _CALL_SITE_INFO *
0x18004a352  mov     [rax], r13d
0x18004a355  call    ?FusionpTraceWin32LastErrorFailure@@YAXAEBU_CALL_SITE_INFO@@@Z; FusionpTraceWin32LastErrorFailure(_CALL_SITE_INFO const &)
0x18004a35a  jmp     loc_18004A146
0x18004a35f  add     rcx, 0C8h; this
0x18004a366  mov     rdx, rbx; struct CDequeLinkage *
0x18004a369  call    ?Remove@?$CDeque@U_COM_SERVER_ENTRY@@$0A@@@QEAAXPEAU_COM_SERVER_ENTRY@@@Z; CDeque<_COM_SERVER_ENTRY,0>::Remove(_COM_SERVER_ENTRY *)
0x18004a36e  mov     rdx, [rbx+20h]; struct CDequeLinkage *
0x18004a372  cmp     [rdx+0E8h], r13
0x18004a379  jnz     loc_18004A22E
0x18004a37f  lea     rcx, [rsi+0A8h]; this
0x18004a386  call    ?Remove@?$CDeque@U_COM_FILE_CONTEXT@@$0A@@@QEAAXPEAU_COM_FILE_CONTEXT@@@Z; CDeque<_COM_FILE_CONTEXT,0>::Remove(_COM_FILE_CONTEXT *)
0x18004a38b  mov     rdi, [rbx+20h]
0x18004a38f  test    rdi, rdi
0x18004a392  jz      short loc_18004A3A4
0x18004a394  mov     rcx, rdi; this
0x18004a397  call    ??1_COM_FILE_CONTEXT@@QEAA@XZ; _COM_FILE_CONTEXT::~_COM_FILE_CONTEXT(void)
0x18004a39c  mov     rcx, rdi; void *
0x18004a39f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18004a3a4  mov     [rbx+20h], r13
0x18004a3a8  jmp     loc_18004A22E
0x18004a3ad  lea     rax, ds:7Ah[rdx*2]
0x18004a3b5  mov     [rbx+8], rax
0x18004a3b9  jmp     loc_18004A132
0x18004a3be  mov     ecx, 54Fh; dwErrCode
0x18004a3c3  call    cs:__imp_SetLastError
0x18004a3ca  nop     dword ptr [rax+rax+00h]
0x18004a3cf  mov     rax, [rbp+57h+var_48]
0x18004a3d3  mov     [rax], r13d
0x18004a3d6  jmp     loc_18004A146
0x18004a3db  lea     r8, [rax+2Ch]
0x18004a3df  mov     [rbx+8], r8
0x18004a3e3  mov     rdx, [rcx+1C0h]
0x18004a3ea  test    rdx, rdx
0x18004a3ed  jnz     loc_18004A74C
0x18004a3f3  cmp     [rcx+1DCh], r13b
0x18004a3fa  jz      loc_18004A75D
0x18004a400  mov     rax, [rcx+150h]
0x18004a407  test    rax, rax
0x18004a40a  jz      loc_18004A13F
0x18004a410  inc     rax
0x18004a413  lea     rax, [r8+rax*2]
0x18004a417  mov     [rbx+8], rax
0x18004a41b  jmp     loc_18004A13F
0x18004a420  cmp     edi, 2
0x18004a423  jnz     loc_18004A13F
0x18004a429  test    rsi, rsi
0x18004a42c  jz      short loc_18004A3BE
0x18004a42e  mov     rax, [rbx+8]
0x18004a432  mov     [rbp+57h+var_80], rax
0x18004a436  mov     rax, [rbx+10h]
0x18004a43a  mov     [rbp+57h+var_90], rax
0x18004a43e  mov     [rbp+57h+var_88], r13
0x18004a442  cmp     [rsi+0F0h], r13
0x18004a449  jnz     loc_18004A560
0x18004a44f  add     rsi, 0A8h
0x18004a456  mov     rdi, [rsi]
0x18004a459  test    rdi, rdi
0x18004a45c  jz      short loc_18004A467
0x18004a45e  cmp     rdi, rsi
0x18004a461  jnz     loc_18004A5C6
0x18004a467  mov     rax, [rbp+57h+var_88]
0x18004a46b  mov     [rbx+18h], rax
0x18004a46f  jmp     loc_18004A13F
0x18004a474  mov     rax, [rbp+57h+var_90]
0x18004a478  mov     [rbx+20h], rax
0x18004a47c  jmp     loc_18004A13F
0x18004a481  cmp     rcx, 2Ch ; ','
0x18004a485  jb      loc_18004A64F
0x18004a48b  lea     rax, [rcx-2Ch]
0x18004a48f  mov     [rbp+57h+var_90], 0A4h
0x18004a497  mov     [rbp+57h+var_80], rax
0x18004a49b  xor     ecx, ecx; dwErrCode
0x18004a49d  lea     rax, [r15+2Ch]
0x18004a4a1  mov     [rbp+57h+var_88], rax
0x18004a4a5  call    cs:__imp_SetLastError
0x18004a4ac  nop     dword ptr [rax+rax+00h]
0x18004a4b1  lea     rax, [r15+14h]
0x18004a4b5  mov     [rsp+30h], rax
0x18004a4ba  lea     rdx, [r15+18h]
0x18004a4be  mov     [rsp+0D0h+var_A8], rdx
0x18004a4c3  lea     rcx, [rsi+130h]
0x18004a4ca  lea     rdx, [rbp+57h+var_88]
0x18004a4ce  mov     [rsp+0D0h+var_B0], r15
0x18004a4d3  lea     r9, [rbp+57h+var_90]
0x18004a4d7  lea     r8, [rbp+57h+var_80]
0x18004a4db  call    ?Win32CopyIntoBuffer@?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@QEBAHPEAPEAGPEA_K1PEAXPEAK3@Z; CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32CopyIntoBuffer(ushort * *,unsigned __int64 *,unsigned __int64 *,void *,ulong *,ulong *)
0x18004a4e0  test    eax, eax
0x18004a4e2  jz      loc_18004A678
0x18004a4e8  mov     rax, [rsi+20h]
0x18004a4ec  mov     ecx, [rax+40h]
0x18004a4ef  add     ecx, ecx
0x18004a4f1  mov     [r15+0Ch], ecx
0x18004a4f5  mov     rax, [rsi+20h]
0x18004a4f9  mov     ecx, [rax+0F0h]
0x18004a4ff  mov     [r15+10h], ecx
0x18004a503  xor     ecx, ecx; dwErrCode
0x18004a505  call    cs:__imp_SetLastError
0x18004a50c  nop     dword ptr [rax+rax+00h]
0x18004a511  lea     rax, [r15+1Ch]
0x18004a515  mov     [rsp+30h], rax
0x18004a51a  lea     rdx, [r15+20h]
0x18004a51e  mov     [rsp+0D0h+var_A8], rdx
0x18004a523  lea     rcx, [rsi+1A0h]
0x18004a52a  lea     rdx, [rbp+57h+var_88]
0x18004a52e  mov     [rsp+0D0h+var_B0], r15
0x18004a533  lea     r9, [rbp+57h+var_90]
0x18004a537  lea     r8, [rbp+57h+var_80]
0x18004a53b  call    ?Win32CopyIntoBuffer@?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@QEBAHPEAPEAGPEA_K1PEAXPEAK3@Z; CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32CopyIntoBuffer(ushort * *,unsigned __int64 *,unsigned __int64 *,void *,ulong *,ulong *)
0x18004a540  test    eax, eax
0x18004a542  jnz     loc_18004A690
0x18004a548  mov     rax, [rbp+57h+var_48]
0x18004a54c  lea     rcx, off_180071A30; struct _CALL_SITE_INFO *
0x18004a553  mov     [rax], r13d
0x18004a556  call    ?FusionpTraceWin32LastErrorFailure@@YAXAEBU_CALL_SITE_INFO@@@Z; FusionpTraceWin32LastErrorFailure(_CALL_SITE_INFO const &)
0x18004a55b  jmp     loc_18004A146
0x18004a560  xor     ecx, ecx; dwErrCode
0x18004a562  call    cs:__imp_SetLastError
0x18004a569  nop     dword ptr [rax+rax+00h]
0x18004a56e  lea     rax, [rsi+10Ch]
0x18004a575  mov     [rsp+30h], rax
0x18004a57a  lea     rdx, [rsi+108h]
0x18004a581  mov     rax, [rbx]
0x18004a584  lea     r9, [rbp+57h+var_88]
0x18004a588  mov     [rsp+0D0h+var_A8], rdx
0x18004a58d  lea     r8, [rbp+57h+var_80]
0x18004a591  lea     rdx, [rbp+57h+var_90]
0x18004a595  mov     [rsp+0D0h+var_B0], rax
0x18004a59a  lea     rcx, [rsi+0D0h]
0x18004a5a1  call    ?Win32CopyIntoBuffer@?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@QEBAHPEAPEAGPEA_K1PEAXPEAK3@Z; CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32CopyIntoBuffer(ushort * *,unsigned __int64 *,unsigned __int64 *,void *,ulong *,ulong *)
0x18004a5a6  test    eax, eax
  ... truncated ...
```
