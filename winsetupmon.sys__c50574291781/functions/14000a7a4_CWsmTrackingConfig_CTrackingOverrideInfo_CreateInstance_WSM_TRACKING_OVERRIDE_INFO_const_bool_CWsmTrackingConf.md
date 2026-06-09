# CWsmTrackingConfig::CTrackingOverrideInfo::CreateInstance(_WSM_TRACKING_OVERRIDE_INFO * const,bool,CWsmTrackingConfig::CTrackingOverrideInfo * *)

- ea: `0x14000a7a4`
- end: `0x14000a8bb`
- name: `?CreateInstance@CTrackingOverrideInfo@CWsmTrackingConfig@@SAJQEAU_WSM_TRACKING_OVERRIDE_INFO@@_NPEAPEAV12@@Z`
- size: `279`
- prototype: `__int64 __fastcall(struct _WSM_TRACKING_OVERRIDE_INFO *const, bool, struct CWsmTrackingConfig::CTrackingOverrideInfo **)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x140009b70`
- `0x14000adb8`

## callees

- `0x140009120`
- `0x140009368`
- `0x14000a7a4`
- `0x14000ce88`
- `0x14000f9e0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000a89a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000a89a`

## pseudocode

```c
__int64 __fastcall CWsmTrackingConfig::CTrackingOverrideInfo::CreateInstance(
        const unsigned __int16 **a1,
        const struct std::nothrow_t *a2,
        void ****a3)
{
  char v5; // bp
  char *v6; // rax
  void ***v7; // rbx
  int v8; // edi
  const unsigned __int16 *v9; // rdx
  wsm_wstring *v10; // rcx
  int v11; // eax
  void **v12; // rax
  void **v13; // rcx
  void **v14; // rax
  void **v15; // rcx

  v5 = (char)a2;
  v6 = (char *)operator new(0x40u, a2);
  v7 = (void ***)v6;
  if ( v6 )
  {
    *(_QWORD *)v6 = &CWsmTrackingConfig::CTrackingOverrideInfo::`vftable';
    v8 = 0;
    *((_QWORD *)v6 + 2) = 0;
    *((_QWORD *)v6 + 1) = &wsm_stable_path::`vftable';
    *((_QWORD *)v6 + 3) = &wsm_wstring::`vftable';
    *((_QWORD *)v6 + 4) = 0;
    *(_OWORD *)(v6 + 40) = 0;
    *((_QWORD *)v6 + 7) = 0;
    if ( a1 )
    {
      v9 = *a1;
      v10 = (wsm_wstring *)(v6 + 8);
      if ( v5 )
        v11 = wsm_wstring::init(v10, v9);
      else
        v11 = (*(__int64 (__fastcall **)(wsm_wstring *, const unsigned __int16 *))(*(_QWORD *)v10 + 16LL))(v10, v9);
      v8 = v11;
      if ( v11 < 0
        || ((v12 = v7[2]) == 0 ? (v13 = 0) : (v13 = (void **)*v12),
            v7[5] = v13,
            v8 = ((__int64 (__fastcall *)(char *, const unsigned __int16 *))v7[3][2])((char *)v7 + 24, a1[1]),
            v8 < 0) )
      {
        CWsmTrackingConfig::CTrackingOverrideInfo::~CTrackingOverrideInfo(v7);
        ExFreePoolWithTag(v7, 0x6E6D7377u);
        return (unsigned int)v8;
      }
      v14 = v7[4];
      if ( v14 )
        v15 = (void **)*v14;
      else
        v15 = 0;
      v7[6] = v15;
      *((_BYTE *)v7 + 56) = *((_BYTE *)a1 + 16);
      *((_DWORD *)v7 + 15) = *((_DWORD *)a1 + 5);
    }
    *a3 = v7;
    return (unsigned int)v8;
  }
  return 3221225626LL;
}

```

## disassembly

```asm
0x14000a7a4  push    rbx
0x14000a7a6  push    rbp
0x14000a7a7  push    rsi
0x14000a7a8  push    rdi
0x14000a7a9  push    r14
0x14000a7ab  sub     rsp, 20h
0x14000a7af  mov     rsi, rcx
0x14000a7b2  mov     r14, r8
0x14000a7b5  mov     ecx, 40h ; '@'; NumberOfBytes
0x14000a7ba  mov     bpl, dl
0x14000a7bd  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x14000a7c2  mov     rbx, rax
0x14000a7c5  test    rax, rax
0x14000a7c8  jz      loc_14000A8AA
0x14000a7ce  lea     rax, ??_7CTrackingOverrideInfo@CWsmTrackingConfig@@6B@; const CWsmTrackingConfig::CTrackingOverrideInfo::`vftable'
0x14000a7d5  xorps   xmm0, xmm0
0x14000a7d8  mov     [rbx], rax
0x14000a7db  xor     edi, edi
0x14000a7dd  mov     qword ptr [rbx+10h], 0
0x14000a7e5  lea     rax, ??_7wsm_stable_path@@6B@; const wsm_stable_path::`vftable'
0x14000a7ec  mov     [rbx+8], rax
0x14000a7f0  lea     rax, ??_7wsm_wstring@@6B@; const wsm_wstring::`vftable'
0x14000a7f7  mov     [rbx+18h], rax
0x14000a7fb  xor     eax, eax
0x14000a7fd  mov     qword ptr [rbx+20h], 0
0x14000a805  movups  xmmword ptr [rbx+28h], xmm0
0x14000a809  mov     [rbx+38h], rax
0x14000a80d  test    rsi, rsi
0x14000a810  jz      short loc_14000A885
0x14000a812  mov     rdx, [rsi]; unsigned __int16 *
0x14000a815  lea     rcx, [rbx+8]; this
0x14000a819  test    bpl, bpl
0x14000a81c  jz      short loc_14000A825
0x14000a81e  call    ?init@wsm_wstring@@IEAAJPEBG@Z; wsm_wstring::init(ushort const *)
0x14000a823  jmp     short loc_14000A831
0x14000a825  mov     rax, [rcx]
0x14000a828  mov     rax, [rax+10h]
0x14000a82c  call    _guard_dispatch_icall
0x14000a831  mov     edi, eax
0x14000a833  test    eax, eax
0x14000a835  js      short loc_14000A88A
0x14000a837  mov     rax, [rbx+10h]
0x14000a83b  test    rax, rax
0x14000a83e  jz      short loc_14000A845
0x14000a840  mov     rcx, [rax]
0x14000a843  jmp     short loc_14000A847
0x14000a845  xor     ecx, ecx
0x14000a847  mov     [rbx+28h], rcx
0x14000a84b  lea     rcx, [rbx+18h]
0x14000a84f  mov     rax, [rcx]
0x14000a852  mov     rdx, [rsi+8]
0x14000a856  mov     rax, [rax+10h]
0x14000a85a  call    _guard_dispatch_icall
0x14000a85f  mov     edi, eax
0x14000a861  test    eax, eax
0x14000a863  js      short loc_14000A88A
0x14000a865  mov     rax, [rbx+20h]
0x14000a869  test    rax, rax
0x14000a86c  jz      short loc_14000A873
0x14000a86e  mov     rcx, [rax]
0x14000a871  jmp     short loc_14000A875
0x14000a873  xor     ecx, ecx
0x14000a875  mov     [rbx+30h], rcx
0x14000a879  mov     al, [rsi+10h]
0x14000a87c  mov     [rbx+38h], al
0x14000a87f  mov     eax, [rsi+14h]
0x14000a882  mov     [rbx+3Ch], eax
0x14000a885  mov     [r14], rbx
0x14000a888  jmp     short loc_14000A8A6
0x14000a88a  mov     rcx, rbx; this
0x14000a88d  call    ??1CTrackingOverrideInfo@CWsmTrackingConfig@@QEAA@XZ; CWsmTrackingConfig::CTrackingOverrideInfo::~CTrackingOverrideInfo(void)
0x14000a892  mov     edx, 6E6D7377h; Tag
0x14000a897  mov     rcx, rbx; P
0x14000a89a  call    cs:__imp_ExFreePoolWithTag
0x14000a8a1  nop     dword ptr [rax+rax+00h]
0x14000a8a6  mov     eax, edi
0x14000a8a8  jmp     short loc_14000A8AF
0x14000a8aa  mov     eax, 0C000009Ah
0x14000a8af  add     rsp, 20h
0x14000a8b3  pop     r14
0x14000a8b5  pop     rdi
0x14000a8b6  pop     rsi
0x14000a8b7  pop     rbp
0x14000a8b8  pop     rbx
0x14000a8b9  retn
```
