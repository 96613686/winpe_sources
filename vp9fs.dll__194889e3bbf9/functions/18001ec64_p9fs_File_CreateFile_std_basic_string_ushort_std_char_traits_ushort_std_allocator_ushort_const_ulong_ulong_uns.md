# p9fs::File::CreateFile(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,ulong,ulong,unsigned __int64,ulong,ulong,p9fs::util::OpenFileFlags,gsl::span<gsl::byte,-1>,p9fs::util::OpenFileOutputFlags *)

- ea: `0x18001ec64`
- end: `0x18001eeab`
- name: `?CreateFile@File@p9fs@@AEAA?AV?$BasicExpected@V?$tuple@V?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@UQid@p9fs@@K@std@@J@util@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KK_KKKW4OpenFileFlags@42@V?$span@W4byte@gsl@@$0?0@gsl@@PEAW4OpenFileOutputFlags@42@@Z`
- size: `583`
- prototype: ``
- caller_count: `3`
- callee_count: `7`
- tags: `file_ops, loader_planting`

## callers

- `0x18001e730`
- `0x18001eaa0`
- `0x1800218b0`

## callees

- `0x180004120`
- `0x1800074e0`
- `0x18001c93c`
- `0x18001ec64`
- `0x18001f0d8`
- `0x18001f940`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ee55`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ee55`
- `lxutil!LxUtilFsCreateMetadataEaBuffer` at `0x18001ed3a`
- `lxutil!LxUtilFsCreateMetadataEaBuffer` at `0x18001ed3a`

## pseudocode

```c
__int64 __fastcall p9fs::File::CreateFile(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        unsigned int a4,
        unsigned int a5,
        __int64 a6,
        int a7,
        int a8,
        int a9,
        __int128 *a10,
        __int64 a11)
{
  __int64 v11; // r10
  __int64 v15; // r8
  int v16; // eax
  unsigned int MetadataEaBuffer; // eax
  gsl::details *v19; // rcx
  int v20; // eax
  int v21; // edx
  __int128 v22; // xmm0
  __int64 v23; // rax
  __int64 *v24; // rcx
  __int64 v25; // r8
  __int64 v26; // rax
  const char *v27; // r9
  int v28; // eax
  __int64 v29; // xmm0_8
  int v30; // eax
  HANDLE v31; // rax
  _QWORD v32[2]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v33; // [rsp+74h] [rbp-8Ch] BYREF
  unsigned int v34; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v35[8]; // [rsp+80h] [rbp-80h] BYREF
  HANDLE hObject; // [rsp+88h] [rbp-78h]
  _BYTE v37[20]; // [rsp+90h] [rbp-70h] BYREF
  int v38; // [rsp+A4h] [rbp-5Ch]
  _BYTE v39[96]; // [rsp+B0h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+168h] [rbp+68h]

  v11 = a11;
  v32[0] = a2;
  v15 = *(_QWORD *)(a1 + 72);
  v32[0] = a11;
  if ( (*(_BYTE *)(v15 + 48) & 4) != 0 && (*(_DWORD *)(v15 + 40) & 0x1000) != 0 )
  {
    v33 = a5;
    v34 = a4;
    v16 = p9fs::File::DetermineCreationInfo((p9fs::File *)a1, &v33, &v34);
    if ( v16 < 0 )
    {
      *(_BYTE *)a2 = 0;
LABEL_5:
      *(_DWORD *)(a2 + 8) = v16;
      return a2;
    }
    MetadataEaBuffer = LxUtilFsCreateMetadataEaBuffer(*(unsigned int *)(a1 + 92), v34, v33, a6, v39);
    v15 = *(_QWORD *)(a1 + 72);
    v19 = (gsl::details *)MetadataEaBuffer;
    v11 = v32[0];
  }
  else
  {
    v19 = 0;
  }
  v20 = a5 & 0xF000;
  if ( v20 == 0x4000 )
  {
    v21 = a9 | 1;
    if ( (*(_BYTE *)(v15 + 48) & 8) != 0 && (*(_DWORD *)(v15 + 40) & 0x2000) != 0 )
      v21 = a9 | 3;
  }
  else if ( v20 != 0x8000 || (a5 & 0x92) != 0 )
  {
    v21 = a9;
  }
  else
  {
    v21 = a9 | 8;
  }
  if ( (unsigned int)v19 > 0x54 )
    gsl::details::terminate(v19);
  v22 = *a10;
  v23 = (unsigned int)v19;
  v24 = *(__int64 **)(v15 + 112);
  v25 = *(_QWORD *)(v15 + 24);
  v32[0] = v23;
  v32[1] = v39;
  v26 = *v24;
  *(_OWORD *)v37 = v22;
  (*(void (__fastcall **)(__int64 *, _BYTE *, __int64, __int64, int, int, int, _QWORD *, _BYTE *, __int64))(v26 + 8))(
    v24,
    v35,
    v25,
    a3,
    a7 | 0x20088,
    a8,
    v21,
    v32,
    v37,
    v11);
  if ( !v35[0] )
  {
    v16 = (int)hObject;
    *(_BYTE *)a2 = 0;
    goto LABEL_5;
  }
  p9fs::GetFileQidByHandle(v37, hObject, a5);
  if ( v37[0] )
  {
    if ( !v35[0] )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x139,
        (unsigned int)"onecore\\vm\\inc\\expected.h",
        v27);
    v28 = *(_DWORD *)&v37[8];
    v29 = *(_QWORD *)&v37[12];
    *(_BYTE *)a2 = 1;
    *(_DWORD *)(a2 + 16) = v28;
    v30 = v38;
    *(_QWORD *)(a2 + 20) = v29;
    *(_DWORD *)(a2 + 28) = v30;
    v31 = hObject;
    *(_DWORD *)(a2 + 8) = a5;
    *(_QWORD *)(a2 + 32) = v31;
  }
  else
  {
    *(_DWORD *)(a2 + 8) = *(_DWORD *)&v37[8];
    *(_BYTE *)a2 = 0;
    if ( v35[0] && (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(hObject);
  }
  return a2;
}

```

## disassembly

```asm
0x18001ec64  push    rbp
0x18001ec66  push    rbx
0x18001ec67  push    rsi
0x18001ec68  push    rdi
0x18001ec69  push    r12
0x18001ec6b  push    r13
0x18001ec6d  push    r14
0x18001ec6f  push    r15
0x18001ec71  lea     rbp, [rsp-28h]
0x18001ec76  sub     rsp, 128h
0x18001ec7d  mov     rax, cs:__security_cookie
0x18001ec84  xor     rax, rsp
0x18001ec87  mov     [rbp+60h+var_50], rax
0x18001ec8b  mov     r10, [rbp+60h+arg_50]
0x18001ec92  mov     r15, r8
0x18001ec95  mov     r14d, [rbp+60h+arg_30]
0x18001ec9c  mov     rbx, rdx
0x18001ec9f  mov     r12d, [rbp+60h+arg_38]
0x18001eca6  mov     rsi, rcx
0x18001eca9  mov     r13, [rbp+60h+arg_48]
0x18001ecb0  mov     edi, [rbp+60h+arg_20]
0x18001ecb6  mov     [rsp+160h+var_100], rdx
0x18001ecbb  mov     r8, [rcx+48h]
0x18001ecbf  mov     [rsp+160h+var_100], r10
0x18001ecc4  test    byte ptr [r8+30h], 4
0x18001ecc9  jz      loc_18001ED4F
0x18001eccf  test    dword ptr [r8+28h], 1000h
0x18001ecd7  jz      short loc_18001ED4F
0x18001ecd9  lea     r8, [rsp+160h+var_E8]; unsigned int *
0x18001ecde  mov     [rsp+160h+var_EC], edi
0x18001ece2  lea     rdx, [rsp+160h+var_EC]; unsigned int *
0x18001ece7  mov     [rsp+160h+var_E8], r9d
0x18001ecec  call    ?DetermineCreationInfo@File@p9fs@@AEAAJAEAK0@Z; p9fs::File::DetermineCreationInfo(ulong &,ulong &)
0x18001ecf1  test    eax, eax
0x18001ecf3  jns     short loc_18001ED1E
0x18001ecf5  mov     byte ptr [rbx], 0
0x18001ecf8  mov     [rbx+8], eax
0x18001ecfb  mov     rax, rbx
0x18001ecfe  mov     rcx, [rbp+60h+var_50]
0x18001ed02  xor     rcx, rsp; StackCookie
0x18001ed05  call    __security_check_cookie
0x18001ed0a  add     rsp, 128h
0x18001ed11  pop     r15
0x18001ed13  pop     r14
0x18001ed15  pop     r13
0x18001ed17  pop     r12
0x18001ed19  pop     rdi
0x18001ed1a  pop     rsi
0x18001ed1b  pop     rbx
0x18001ed1c  pop     rbp
0x18001ed1d  retn
0x18001ed1e  mov     r9, [rbp+60h+arg_28]
0x18001ed25  lea     rax, [rbp+60h+var_B0]
0x18001ed29  mov     r8d, [rsp+160h+var_EC]
0x18001ed2e  mov     edx, [rsp+160h+var_E8]
0x18001ed32  mov     ecx, [rsi+5Ch]
0x18001ed35  mov     [rsp+160h+var_140], rax
0x18001ed3a  call    cs:__imp_LxUtilFsCreateMetadataEaBuffer
0x18001ed40  mov     r8, [rsi+48h]
0x18001ed44  mov     ecx, eax
0x18001ed46  mov     r10, [rsp+160h+var_100]
0x18001ed4b  xor     esi, esi
0x18001ed4d  jmp     short loc_18001ED53
0x18001ed4f  xor     esi, esi
0x18001ed51  mov     ecx, esi; this
0x18001ed53  mov     eax, edi
0x18001ed55  and     eax, 0F000h
0x18001ed5a  cmp     eax, 4000h
0x18001ed5f  jnz     short loc_18001ED80
0x18001ed61  mov     edx, [rbp+60h+arg_40]
0x18001ed67  or      edx, 1
0x18001ed6a  test    byte ptr [r8+30h], 8
0x18001ed6f  jz      short loc_18001ED9E
0x18001ed71  test    dword ptr [r8+28h], 2000h
0x18001ed79  jz      short loc_18001ED9E
0x18001ed7b  or      edx, 2
0x18001ed7e  jmp     short loc_18001ED9E
0x18001ed80  cmp     eax, 8000h
0x18001ed85  jnz     short loc_18001ED98
0x18001ed87  test    dil, 92h
0x18001ed8b  jnz     short loc_18001ED98
0x18001ed8d  mov     edx, [rbp+60h+arg_40]
0x18001ed93  or      edx, 8
0x18001ed96  jmp     short loc_18001ED9E
0x18001ed98  mov     edx, [rbp+60h+arg_40]
0x18001ed9e  cmp     ecx, 54h ; 'T'
0x18001eda1  ja      loc_18001EEA5
0x18001eda7  movaps  xmm0, xmmword ptr [r13+0]
0x18001edac  lea     r9, [rbp+60h+var_D0]
0x18001edb0  mov     [rsp+160h+var_118], r10
0x18001edb5  or      r14d, 20088h
0x18001edbc  mov     [rsp+160h+var_120], r9
0x18001edc1  lea     r9, [rsp+160h+var_100]
0x18001edc6  mov     [rsp+160h+var_128], r9
0x18001edcb  mov     r9, r15
0x18001edce  mov     eax, ecx
0x18001edd0  mov     rcx, [r8+70h]
0x18001edd4  mov     r8, [r8+18h]
0x18001edd8  mov     [rsp+160h+var_100], rax
0x18001eddd  lea     rax, [rbp+60h+var_B0]
0x18001ede1  mov     [rsp+160h+var_130], edx
0x18001ede5  lea     rdx, [rbp+60h+var_E0]
0x18001ede9  mov     [rsp+160h+var_F8], rax
0x18001edee  mov     rax, [rcx]
0x18001edf1  mov     [rsp+160h+var_138], r12d
0x18001edf6  movdqa  xmmword ptr [rbp+60h+var_D0], xmm0
0x18001edfb  mov     dword ptr [rsp+160h+var_140], r14d
0x18001ee00  mov     rax, [rax+8]
0x18001ee04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ee09  cmp     [rbp+60h+var_E0], sil
0x18001ee0d  jnz     short loc_18001EE1A
0x18001ee0f  mov     eax, dword ptr [rbp+60h+hObject]
0x18001ee12  mov     [rbx], sil
0x18001ee15  jmp     loc_18001ECF8
0x18001ee1a  mov     rdx, [rbp+60h+hObject]
0x18001ee1e  lea     rcx, [rbp+60h+var_D0]
0x18001ee22  mov     r8d, edi
0x18001ee25  call    ?GetFileQidByHandle@p9fs@@YA?AV?$BasicExpected@UQid@p9fs@@J@util@@PEAXK@Z; p9fs::GetFileQidByHandle(void *,ulong)
0x18001ee2a  cmp     [rbp+60h+var_D0], sil
0x18001ee2e  jnz     short loc_18001EE60
0x18001ee30  mov     eax, dword ptr [rbp+60h+var_D0+8]
0x18001ee33  mov     [rbx+8], eax
0x18001ee36  mov     [rbx], sil
0x18001ee39  cmp     [rbp+60h+var_E0], sil
0x18001ee3d  jz      loc_18001ECFB
0x18001ee43  mov     rcx, [rbp+60h+hObject]; hObject
0x18001ee47  lea     rax, [rcx-1]
0x18001ee4b  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001ee4f  ja      loc_18001ECFB
0x18001ee55  call    cs:__imp_CloseHandle
0x18001ee5b  jmp     loc_18001ECFB
0x18001ee60  cmp     [rbp+60h+var_E0], sil
0x18001ee64  jz      short loc_18001EE8F
0x18001ee66  mov     eax, dword ptr [rbp+60h+var_D0+8]
0x18001ee69  movsd   xmm0, qword ptr [rbp+60h+var_D0+0Ch]
0x18001ee6e  mov     byte ptr [rbx], 1
0x18001ee71  mov     [rbx+10h], eax
0x18001ee74  mov     eax, [rbp+60h+var_BC]
0x18001ee77  movsd   qword ptr [rbx+14h], xmm0
0x18001ee7c  mov     [rbx+1Ch], eax
0x18001ee7f  mov     rax, [rbp+60h+hObject]
0x18001ee83  mov     [rbx+8], edi
0x18001ee86  mov     [rbx+20h], rax
0x18001ee8a  jmp     loc_18001ECFB
0x18001ee8f  mov     rcx, [rbp+68h]; this
0x18001ee93  lea     r8, aOnecoreVmIncEx; "onecore\\vm\\inc\\expected.h"
0x18001ee9a  mov     edx, 139h; void *
0x18001ee9f  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18001eea5  call    ?terminate@details@gsl@@YAXXZ; gsl::details::terminate(void)
```
