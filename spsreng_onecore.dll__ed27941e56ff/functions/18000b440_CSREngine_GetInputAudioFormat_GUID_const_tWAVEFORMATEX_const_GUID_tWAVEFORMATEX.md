# CSREngine::GetInputAudioFormat(_GUID const *,tWAVEFORMATEX const *,_GUID *,tWAVEFORMATEX * *)

- ea: `0x18000b440`
- end: `0x18000b696`
- name: `?GetInputAudioFormat@CSREngine@@UEAAJPEBU_GUID@@PEBUtWAVEFORMATEX@@PEAU2@PEAPEAU3@@Z`
- size: `598`
- prototype: `__int64 __fastcall(CSREngine *this, const struct _GUID *, struct tWAVEFORMATEX *, struct _GUID *, struct tWAVEFORMATEX **)`
- caller_count: `0`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800034b0`
- `0x180004312`
- `0x18000b440`
- `0x1800207e4`
- `0x180020cec`
- `0x1800210a4`
- `0x180102010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b655`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b655`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000b591`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000b5e3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000b591`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000b5e3`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CSREngine::GetInputAudioFormat(
        CSREngine *this,
        const struct _GUID *a2,
        struct tWAVEFORMATEX *a3,
        struct _GUID *a4,
        struct tWAVEFORMATEX **a5)
{
  CSREngine *v5; // rdi
  WORD cbSize; // r15
  _QWORD *v7; // rax
  __int64 v12; // rax
  __int64 *i; // rdi
  unsigned int PreferredWaveFormat; // r14d
  __int64 v15; // rax
  WORD wFormatTag; // bx
  __int64 v17; // rcx
  struct tWAVEFORMATEX *v18; // rax
  __int64 v19; // r8
  struct tWAVEFORMATEX *v20; // rdx
  struct tWAVEFORMATEX *v21; // rbx
  __int64 v22; // rcx
  DWORD v23; // eax
  bool v24; // [rsp+20h] [rbp-50h] BYREF
  CSREngine *v25; // [rsp+28h] [rbp-48h] BYREF
  struct tWAVEFORMATEX v26; // [rsp+30h] [rbp-40h] BYREF
  struct _GUID v27; // [rsp+48h] [rbp-28h] BYREF
  struct _GUID v28; // [rsp+58h] [rbp-18h] BYREF

  v5 = this;
  v25 = this;
  cbSize = 0;
  v24 = 0;
  v7 = (_QWORD *)*((_QWORD *)this + 87);
  v27 = 0;
  v28 = 0;
  memset(&v26, 0, sizeof(v26));
  if ( !*v7 )
    return 2147500037LL;
  if ( !a2 )
    goto LABEL_29;
  v12 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&SPDFID_WaveFormatEx.Data1;
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&SPDFID_WaveFormatEx.Data1 )
    v12 = *(_QWORD *)a2->Data4 - *(_QWORD *)SPDFID_WaveFormatEx.Data4;
  if ( v12 || !a3 )
  {
    v27 = *a2;
    goto LABEL_11;
  }
  if ( (unsigned int)CFEManager::GUIDFromWaveFormatEx(CFEManager::s_pFEManager, a3, &v27, &v26) )
  {
LABEL_29:
    v21 = (struct tWAVEFORMATEX *)CoTaskMemAlloc(0x12u);
    if ( v21 )
    {
      PreferredWaveFormat = CFEManager::GetPreferredWaveFormatEx(
                              (CFEManager *)CFEManager::s_pFEManager,
                              (const struct _GUID *)(**((_QWORD **)v5 + 87) + 8LL),
                              v21);
      if ( PreferredWaveFormat )
      {
        CoTaskMemFree(v21);
        v21 = 0;
      }
      else
      {
        v22 = *((_QWORD *)v5 + 13);
        LODWORD(v25) = 0;
        if ( !(*(unsigned int (__fastcall **)(__int64, const wchar_t *, CSREngine **))(*(_QWORD *)v22 + 64LL))(
                v22,
                L"PreferredAudioRate",
                &v25) )
        {
          v23 = (_DWORD)v25 * v21->nBlockAlign;
          v21->nSamplesPerSec = (unsigned int)v25;
          v21->nAvgBytesPerSec = v23;
        }
      }
      *a4 = SPDFID_WaveFormatEx;
      *a5 = v21;
      return PreferredWaveFormat;
    }
    return 2147942414LL;
  }
  cbSize = v26.cbSize;
LABEL_11:
  for ( i = (__int64 *)**((_QWORD **)v5 + 87); ; i = (__int64 *)*i )
  {
    if ( !i )
    {
      v5 = v25;
      goto LABEL_29;
    }
    v28 = *(struct _GUID *)(i + 1);
    PreferredWaveFormat = CFEManager::IsMappingSupported((CFEManager *)CFEManager::s_pFEManager, &v27, &v28, &v24);
    if ( PreferredWaveFormat )
      return PreferredWaveFormat;
    if ( v24 )
      break;
  }
  v15 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&SPDFID_WaveFormatEx.Data1;
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&SPDFID_WaveFormatEx.Data1 )
    v15 = *(_QWORD *)a2->Data4 - *(_QWORD *)SPDFID_WaveFormatEx.Data4;
  if ( v15 )
  {
    *a4 = *a2;
    *a5 = 0;
    return PreferredWaveFormat;
  }
  wFormatTag = v26.wFormatTag;
  *a4 = SPDFID_WaveFormatEx;
  if ( wFormatTag )
    v17 = cbSize;
  else
    v17 = a3->cbSize;
  v18 = (struct tWAVEFORMATEX *)CoTaskMemAlloc(v17 + 18);
  *a5 = v18;
  if ( !v18 )
    return 2147942414LL;
  if ( wFormatTag )
  {
    v19 = cbSize;
    v20 = &v26;
  }
  else
  {
    v19 = a3->cbSize;
    v20 = a3;
  }
  memcpy_0(v18, v20, v19 + 18);
  return PreferredWaveFormat;
}

```

## disassembly

```asm
0x18000b440  mov     [rsp-38h+arg_8], rbx
0x18000b445  push    rbp
0x18000b446  push    rsi
0x18000b447  push    rdi
0x18000b448  push    r12
0x18000b44a  push    r13
0x18000b44c  push    r14
0x18000b44e  push    r15
0x18000b450  mov     rbp, rsp
0x18000b453  sub     rsp, 70h
0x18000b457  mov     rax, cs:__security_cookie
0x18000b45e  xor     rax, rsp
0x18000b461  mov     [rbp+var_8], rax
0x18000b465  mov     r13, [rbp+arg_20]
0x18000b469  mov     rdi, rcx
0x18000b46c  xorps   xmm0, xmm0
0x18000b46f  mov     [rbp+var_48], rcx
0x18000b473  xor     ecx, ecx
0x18000b475  xor     r15d, r15d
0x18000b478  xorps   xmm1, xmm1
0x18000b47b  mov     [rbp+var_50], cl
0x18000b47e  mov     rax, [rdi+2B8h]
0x18000b485  mov     r12, r9
0x18000b488  movups  xmmword ptr [rbp+var_28.Data1], xmm0
0x18000b48c  mov     rsi, r8
0x18000b48f  mov     rbx, rdx
0x18000b492  movups  xmmword ptr [rbp+var_18.Data1], xmm1
0x18000b496  mov     [rbp+var_40.cbSize], r15w
0x18000b49b  movups  xmmword ptr [rbp+var_40.wFormatTag], xmm0
0x18000b49f  cmp     [rax], rcx
0x18000b4a2  jnz     short loc_18000B4AE
0x18000b4a4  mov     eax, 80004005h
0x18000b4a9  jmp     loc_18000B672
0x18000b4ae  test    rbx, rbx
0x18000b4b1  jz      loc_18000B5DE
0x18000b4b7  mov     rax, [rdx]
0x18000b4ba  sub     rax, qword ptr cs:SPDFID_WaveFormatEx.Data1
0x18000b4c1  jnz     short loc_18000B4CE
0x18000b4c3  mov     rax, [rdx+8]
0x18000b4c7  sub     rax, qword ptr cs:SPDFID_WaveFormatEx.Data4
0x18000b4ce  test    rax, rax
0x18000b4d1  jnz     short loc_18000B4FE
0x18000b4d3  test    rsi, rsi
0x18000b4d6  jz      short loc_18000B4FE
0x18000b4d8  mov     rcx, cs:?s_pFEManager@CFEManager@@0PEAV1@EA; lpCriticalSection
0x18000b4df  lea     r9, [rbp+var_40]; struct tWAVEFORMATEX *
0x18000b4e3  lea     r8, [rbp+var_28]; struct _GUID *
0x18000b4e7  mov     rdx, rsi; Buf1
0x18000b4ea  call    ?GUIDFromWaveFormatEx@CFEManager@@QEAAJPEBUtWAVEFORMATEX@@PEAU_GUID@@PEAU2@@Z; CFEManager::GUIDFromWaveFormatEx(tWAVEFORMATEX const *,_GUID *,tWAVEFORMATEX *)
0x18000b4ef  test    eax, eax
0x18000b4f1  jnz     loc_18000B5DE
0x18000b4f7  movzx   r15d, [rbp+var_40.cbSize]
0x18000b4fc  jmp     short loc_18000B506
0x18000b4fe  movups  xmm0, xmmword ptr [rdx]
0x18000b501  movdqu  xmmword ptr [rbp+var_28.Data1], xmm0
0x18000b506  mov     rax, [rdi+2B8h]
0x18000b50d  mov     rdi, [rax]
0x18000b510  test    rdi, rdi
0x18000b513  jz      loc_18000B5DA
0x18000b519  movups  xmm0, xmmword ptr [rdi+8]
0x18000b51d  mov     rcx, cs:?s_pFEManager@CFEManager@@0PEAV1@EA; this
0x18000b524  lea     r9, [rbp+var_50]; bool *
0x18000b528  lea     r8, [rbp+var_18]; struct _GUID *
0x18000b52c  lea     rdx, [rbp+var_28]; struct _GUID *
0x18000b530  movdqu  xmmword ptr [rbp+var_18.Data1], xmm0
0x18000b535  call    ?IsMappingSupported@CFEManager@@QEAAJPEBU_GUID@@0PEA_N@Z; CFEManager::IsMappingSupported(_GUID const *,_GUID const *,bool *)
0x18000b53a  xor     ecx, ecx
0x18000b53c  mov     r14d, eax
0x18000b53f  test    eax, eax
0x18000b541  jnz     loc_18000B66F
0x18000b547  cmp     [rbp+var_50], cl
0x18000b54a  jnz     short loc_18000B551
0x18000b54c  mov     rdi, [rdi]
0x18000b54f  jmp     short loc_18000B510
0x18000b551  mov     rax, [rbx]
0x18000b554  sub     rax, qword ptr cs:SPDFID_WaveFormatEx.Data1
0x18000b55b  jnz     short loc_18000B568
0x18000b55d  mov     rax, [rbx+8]
0x18000b561  sub     rax, qword ptr cs:SPDFID_WaveFormatEx.Data4
0x18000b568  test    rax, rax
0x18000b56b  jnz     short loc_18000B5C8
0x18000b56d  movups  xmm0, xmmword ptr cs:SPDFID_WaveFormatEx.Data1
0x18000b574  movzx   ebx, [rbp+var_40.wFormatTag]
0x18000b578  movdqu  xmmword ptr [r12], xmm0
0x18000b57e  test    bx, bx
0x18000b581  jnz     short loc_18000B589
0x18000b583  movzx   ecx, word ptr [rsi+10h]
0x18000b587  jmp     short loc_18000B58D
0x18000b589  movzx   ecx, r15w
0x18000b58d  add     rcx, 12h; cb
0x18000b591  call    cs:__imp_CoTaskMemAlloc
0x18000b597  mov     [r13+0], rax
0x18000b59b  test    rax, rax
0x18000b59e  jz      short loc_18000B5F3
0x18000b5a0  mov     rcx, rax; void *
0x18000b5a3  test    bx, bx
0x18000b5a6  jnz     short loc_18000B5BE
0x18000b5a8  movzx   r8d, word ptr [rsi+10h]
0x18000b5ad  mov     rdx, rsi; Src
0x18000b5b0  add     r8, 12h; Size
0x18000b5b4  call    memcpy_0
0x18000b5b9  jmp     loc_18000B66F
0x18000b5be  movzx   r8d, r15w
0x18000b5c2  lea     rdx, [rbp+var_40]
0x18000b5c6  jmp     short loc_18000B5B0
0x18000b5c8  movups  xmm0, xmmword ptr [rbx]
0x18000b5cb  movdqu  xmmword ptr [r12], xmm0
0x18000b5d1  mov     [r13+0], rcx
0x18000b5d5  jmp     loc_18000B66F
0x18000b5da  mov     rdi, [rbp+var_48]
0x18000b5de  mov     ecx, 12h; cb
0x18000b5e3  call    cs:__imp_CoTaskMemAlloc
0x18000b5e9  xor     esi, esi
0x18000b5eb  mov     rbx, rax
0x18000b5ee  test    rax, rax
0x18000b5f1  jnz     short loc_18000B5FA
0x18000b5f3  mov     eax, 8007000Eh
0x18000b5f8  jmp     short loc_18000B672
0x18000b5fa  mov     rax, [rdi+2B8h]
0x18000b601  mov     r8, rbx; struct tWAVEFORMATEX *
0x18000b604  mov     rcx, cs:?s_pFEManager@CFEManager@@0PEAV1@EA; this
0x18000b60b  mov     rdx, [rax]
0x18000b60e  add     rdx, 8; struct _GUID *
0x18000b612  call    ?GetPreferredWaveFormatEx@CFEManager@@QEAAJPEBU_GUID@@PEAUtWAVEFORMATEX@@@Z; CFEManager::GetPreferredWaveFormatEx(_GUID const *,tWAVEFORMATEX *)
0x18000b617  mov     r14d, eax
0x18000b61a  test    eax, eax
0x18000b61c  jnz     short loc_18000B652
0x18000b61e  mov     rcx, [rdi+68h]
0x18000b622  lea     r8, [rbp+var_48]
0x18000b626  mov     dword ptr [rbp+var_48], esi
0x18000b629  lea     rdx, aPreferredaudio; "PreferredAudioRate"
0x18000b630  mov     rax, [rcx]
0x18000b633  mov     rax, [rax+40h]
0x18000b637  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b63c  test    eax, eax
0x18000b63e  jnz     short loc_18000B65E
0x18000b640  mov     ecx, dword ptr [rbp+var_48]
0x18000b643  movzx   eax, word ptr [rbx+0Ch]
0x18000b647  imul    eax, ecx
0x18000b64a  mov     [rbx+4], ecx
0x18000b64d  mov     [rbx+8], eax
0x18000b650  jmp     short loc_18000B65E
0x18000b652  mov     rcx, rbx; pv
0x18000b655  call    cs:__imp_CoTaskMemFree
0x18000b65b  mov     rbx, rsi
0x18000b65e  movups  xmm0, xmmword ptr cs:SPDFID_WaveFormatEx.Data1
0x18000b665  movdqu  xmmword ptr [r12], xmm0
0x18000b66b  mov     [r13+0], rbx
0x18000b66f  mov     eax, r14d
0x18000b672  mov     rcx, [rbp+var_8]
0x18000b676  xor     rcx, rsp; StackCookie
0x18000b679  call    __security_check_cookie
0x18000b67e  mov     rbx, [rsp+70h+arg_8]
0x18000b686  add     rsp, 70h
0x18000b68a  pop     r15
0x18000b68c  pop     r14
0x18000b68e  pop     r13
0x18000b690  pop     r12
0x18000b692  pop     rdi
0x18000b693  pop     rsi
0x18000b694  pop     rbp
0x18000b695  retn
```
