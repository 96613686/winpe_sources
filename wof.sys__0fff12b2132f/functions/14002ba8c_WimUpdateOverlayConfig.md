# WimUpdateOverlayConfig

- ea: `0x14002ba8c`
- end: `0x14002bde4`
- name: `WimUpdateOverlayConfig`
- size: `856`
- prototype: `__int64 __fastcall(__int64, int, _QWORD *, int, _QWORD *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, installer_update`

## callers

- `0x140027820`

## callees

- `0x14000fce4`
- `0x14001024c`
- `0x1400102bc`
- `0x1400116c0`
- `0x1400119c0`
- `0x14002b404`
- `0x14002b43c`
- `0x14002b73c`
- `0x14002ba8c`
- `0x14002bdec`
- `0x14003c578`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14002bd65`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002bd7b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002bd93`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002bd65`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002bd7b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002bd93`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14002bc23`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14002bc23`
- `ntoskrnl!ObfDereferenceObject` at `0x14002bda8`
- `ntoskrnl!ObfDereferenceObject` at `0x14002bda8`
- `FLTMGR!FltClose` at `0x14002bdbd`
- `FLTMGR!FltClose` at `0x14002bdbd`

## pseudocode

```c
__int64 __fastcall WimUpdateOverlayConfig(__int64 a1, int a2, _QWORD *a3, int a4, _QWORD *a5)
{
  int v5; // r15d
  __int64 v8; // r13
  int v9; // eax
  int v10; // edx
  unsigned int v11; // ebx
  _DWORD *v12; // rdi
  int OverlayConfig; // eax
  _DWORD *v14; // rsi
  PDEVICE_OBJECT v15; // rcx
  int v16; // edx
  __int64 OverlayInfo; // rax
  __int64 v18; // rdx
  __int64 v19; // r8
  __int64 v20; // rcx
  unsigned int v21; // r12d
  SIZE_T v22; // rbx
  _DWORD *PoolWithTag; // rax
  unsigned int v24; // ebx
  bool v25; // zf
  unsigned int v26; // r13d
  __int64 v27; // rcx
  _DWORD *v28; // rdx
  unsigned int v29; // r15d
  int v31; // [rsp+30h] [rbp-30h] BYREF
  PVOID P; // [rsp+38h] [rbp-28h] BYREF
  PVOID Object; // [rsp+40h] [rbp-20h] BYREF
  HANDLE FileHandle; // [rsp+48h] [rbp-18h] BYREF
  void *Src; // [rsp+50h] [rbp-10h] BYREF
  __int64 v36; // [rsp+58h] [rbp-8h]
  unsigned int v38; // [rsp+A8h] [rbp+48h] BYREF

  v5 = a1 + 64;
  v31 = 0;
  v38 = 0;
  v8 = a1;
  P = 0;
  Object = 0;
  FileHandle = 0;
  Src = 0;
  v36 = a1 + 64;
  v9 = WimPathToBootEnvironmentDevice((int)a1 + 64, a2 + 64, a4, (unsigned int)&P, (__int64)&v38);
  v11 = v9;
  if ( v9 < 0 )
  {
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      WPP_SF_Zd(
        WPP_GLOBAL_Control->AttachedDevice,
        50,
        (unsigned int)WPP_8be5f4e5626c39736f1e2e11a2a58b62_Traceguids,
        a4,
        v9);
    goto LABEL_42;
  }
  LOBYTE(v10) = 1;
  v12 = 0;
  OverlayConfig = WimReadOverlayConfig(
                    v8,
                    v10,
                    (unsigned int)&FileHandle,
                    (unsigned int)&Object,
                    (__int64)&Src,
                    (__int64)&v31);
  v14 = Src;
  v11 = OverlayConfig;
  if ( OverlayConfig >= 0 )
  {
    OverlayInfo = WimFindOverlayInfo(Src, a3);
    if ( !OverlayInfo )
    {
      v11 = -1073741275;
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        WPP_SF_id(WPP_GLOBAL_Control->AttachedDevice, v18, v19, *a3);
      goto LABEL_38;
    }
    v20 = *(_QWORD *)(OverlayInfo + 24) - *a5;
    if ( !v20 )
      v20 = *(_QWORD *)(OverlayInfo + 32) - a5[1];
    if ( v20 )
    {
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        WPP_SF_i_guid__guid_(
          WPP_GLOBAL_Control->AttachedDevice,
          OverlayInfo + 24,
          (_DWORD)a5,
          *a3,
          OverlayInfo + 24,
          (__int64)a5);
      v11 = -1073741811;
      goto LABEL_38;
    }
    v21 = v38;
    v22 = v38 + v31;
    PoolWithTag = ExAllocatePoolWithTag(PagedPool, v22, 0x66637077u);
    v12 = PoolWithTag;
    if ( !PoolWithTag )
    {
      v11 = -1073741801;
      goto LABEL_38;
    }
    memset(PoolWithTag, 0, v22);
    v24 = v14[2] * v14[3] + 24;
    memmove(v12, v14, v24);
    v25 = v12[3] == 0;
    v38 = 0;
    if ( !v25 )
    {
      v26 = v38;
      do
      {
        v27 = v12[2] * v26;
        if ( *(_QWORD *)((char *)v12 + v27 + 24) == *a3 )
        {
          v28 = P;
          v29 = v21;
        }
        else
        {
          v28 = (_DWORD *)((char *)v14 + *(unsigned int *)((char *)v12 + v27 + 32));
          v29 = v28[2];
        }
        *(_DWORD *)((char *)v12 + v27 + 32) = v24;
        *(_DWORD *)((char *)v12 + v27 + 36) = v29;
        memmove((char *)v12 + v24, v28, v29);
        v24 += v29;
        ++v26;
      }
      while ( v26 < v12[3] );
      v8 = a1;
      v5 = v36;
    }
    if ( v24 > 0x200000 )
    {
      v11 = -1073740761;
      goto LABEL_38;
    }
    OverlayConfig = WimWriteOverlayConfig(v8, FileHandle, Object, v12, v24);
    v11 = OverlayConfig;
    FileHandle = 0;
    Object = 0;
    if ( OverlayConfig >= 0 )
    {
      WimPublishConfigChangeNotification();
      goto LABEL_38;
    }
    v15 = WPP_GLOBAL_Control;
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) == 0 || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      goto LABEL_38;
    v16 = 54;
  }
  else
  {
    v15 = WPP_GLOBAL_Control;
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) == 0 || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      goto LABEL_38;
    v16 = 51;
  }
  WPP_SF_Zd(v15->AttachedDevice, v16, (unsigned int)WPP_8be5f4e5626c39736f1e2e11a2a58b62_Traceguids, v5, OverlayConfig);
LABEL_38:
  if ( v14 )
    ExFreePoolWithTag(v14, 0);
  if ( v12 )
    ExFreePoolWithTag(v12, 0);
LABEL_42:
  if ( P )
    ExFreePoolWithTag(P, 0);
  if ( Object )
    ObfDereferenceObject(Object);
  if ( FileHandle )
    FltClose(FileHandle);
  return v11;
}

```

## disassembly

```asm
0x14002ba8c  mov     [rsp-38h+arg_10], rbx
0x14002ba91  mov     [rsp-38h+arg_0], rcx
0x14002ba96  push    rbp
0x14002ba97  push    rsi
0x14002ba98  push    rdi
0x14002ba99  push    r12
0x14002ba9b  push    r13
0x14002ba9d  push    r14
0x14002ba9f  push    r15
0x14002baa1  mov     rbp, rsp
0x14002baa4  sub     rsp, 60h
0x14002baa8  xor     r12d, r12d
0x14002baab  lea     r15, [rcx+40h]
0x14002baaf  mov     rdi, r9
0x14002bab2  mov     [rbp+var_30], r12d
0x14002bab6  mov     r14, r8
0x14002bab9  mov     [rbp+arg_8], r12d
0x14002babd  mov     r13, rcx
0x14002bac0  mov     [rbp+P], r12
0x14002bac4  lea     rax, [rbp+arg_8]
0x14002bac8  mov     [rbp+Object], r12
0x14002bacc  mov     r8, rdi
0x14002bacf  mov     [rbp+FileHandle], r12
0x14002bad3  mov     rcx, r15
0x14002bad6  mov     [rbp+Src], r12
0x14002bada  add     rdx, 40h ; '@'
0x14002bade  mov     [rbp+var_8], r15
0x14002bae2  lea     r9, [rbp+P]
0x14002bae6  mov     [rsp+60h+var_40], rax
0x14002baeb  call    WimPathToBootEnvironmentDevice
0x14002baf0  mov     ebx, eax
0x14002baf2  test    eax, eax
0x14002baf4  jns     short loc_14002BB35
0x14002baf6  mov     rcx, cs:WPP_GLOBAL_Control
0x14002bafd  test    dword ptr [rcx+2Ch], 400h
0x14002bb04  jz      loc_14002BD87
0x14002bb0a  cmp     byte ptr [rcx+29h], 2
0x14002bb0e  jb      loc_14002BD87
0x14002bb14  mov     rcx, [rcx+18h]
0x14002bb18  lea     edx, [r12+32h]
0x14002bb1d  mov     r9, rdi
0x14002bb20  mov     dword ptr [rsp+60h+var_40], eax
0x14002bb24  lea     r8, WPP_8be5f4e5626c39736f1e2e11a2a58b62_Traceguids
0x14002bb2b  call    WPP_SF_Zd
0x14002bb30  jmp     loc_14002BD87
0x14002bb35  lea     rax, [rbp+var_30]
0x14002bb39  mov     dl, 1
0x14002bb3b  mov     [rsp+60h+var_38], rax
0x14002bb40  lea     r9, [rbp+Object]
0x14002bb44  lea     rax, [rbp+Src]
0x14002bb48  mov     rcx, r13
0x14002bb4b  lea     r8, [rbp+FileHandle]
0x14002bb4f  mov     [rsp+60h+var_40], rax
0x14002bb54  mov     rdi, r12
0x14002bb57  call    WimReadOverlayConfig
0x14002bb5c  mov     rsi, [rbp+Src]
0x14002bb60  mov     ebx, eax
0x14002bb62  test    eax, eax
0x14002bb64  jns     short loc_14002BBA5
0x14002bb66  mov     rcx, cs:WPP_GLOBAL_Control
0x14002bb6d  test    dword ptr [rcx+2Ch], 400h
0x14002bb74  jz      loc_14002BD5B
0x14002bb7a  cmp     byte ptr [rcx+29h], 2
0x14002bb7e  jb      loc_14002BD5B
0x14002bb84  mov     edx, 33h ; '3'
0x14002bb89  mov     rcx, [rcx+18h]
0x14002bb8d  lea     r8, WPP_8be5f4e5626c39736f1e2e11a2a58b62_Traceguids
0x14002bb94  mov     r9, r15
0x14002bb97  mov     dword ptr [rsp+60h+var_40], eax
0x14002bb9b  call    WPP_SF_Zd
0x14002bba0  jmp     loc_14002BD5B
0x14002bba5  mov     rdx, r14
0x14002bba8  mov     rcx, rsi
0x14002bbab  call    WimFindOverlayInfo
0x14002bbb0  test    rax, rax
0x14002bbb3  jnz     short loc_14002BBE9
0x14002bbb5  mov     ebx, 0C0000225h
0x14002bbba  mov     rcx, cs:WPP_GLOBAL_Control
0x14002bbc1  test    dword ptr [rcx+2Ch], 400h
0x14002bbc8  jz      loc_14002BD5B
0x14002bbce  cmp     byte ptr [rcx+29h], 2
0x14002bbd2  jb      loc_14002BD5B
0x14002bbd8  mov     r9, [r14]
0x14002bbdb  mov     rcx, [rcx+18h]
0x14002bbdf  call    WPP_SF_id
0x14002bbe4  jmp     loc_14002BD5B
0x14002bbe9  mov     r8, [rbp+arg_20]
0x14002bbed  lea     rdx, [rax+18h]
0x14002bbf1  mov     rcx, [rdx]
0x14002bbf4  sub     rcx, [r8]
0x14002bbf7  jnz     short loc_14002BC01
0x14002bbf9  mov     rcx, [rdx+8]
0x14002bbfd  sub     rcx, [r8+8]
0x14002bc01  test    rcx, rcx
0x14002bc04  jnz     loc_14002BD2A
0x14002bc0a  mov     ecx, [rbp+var_30]
0x14002bc0d  mov     r8d, 66637077h; Tag
0x14002bc13  mov     r12d, [rbp+arg_8]
0x14002bc17  add     ecx, r12d
0x14002bc1a  mov     ebx, ecx
0x14002bc1c  mov     edx, ecx; NumberOfBytes
0x14002bc1e  mov     ecx, 1; PoolType
0x14002bc23  call    cs:__imp_ExAllocatePoolWithTag
0x14002bc2a  nop     dword ptr [rax+rax+00h]
0x14002bc2f  mov     rdi, rax
0x14002bc32  test    rax, rax
0x14002bc35  jnz     short loc_14002BC44
0x14002bc37  mov     ebx, 0C0000017h
0x14002bc3c  xor     r12d, r12d
0x14002bc3f  jmp     loc_14002BD5B
0x14002bc44  mov     r8, rbx; Size
0x14002bc47  xor     edx, edx; Val
0x14002bc49  mov     rcx, rdi; void *
0x14002bc4c  call    memset
0x14002bc51  mov     ebx, [rsi+0Ch]
0x14002bc54  mov     rdx, rsi; Src
0x14002bc57  imul    ebx, [rsi+8]
0x14002bc5b  mov     rcx, rdi; void *
0x14002bc5e  add     ebx, 18h
0x14002bc61  mov     r8d, ebx; Size
0x14002bc64  call    memmove
0x14002bc69  cmp     dword ptr [rdi+0Ch], 0
0x14002bc6d  mov     [rbp+arg_8], 0
0x14002bc74  jbe     short loc_14002BCC9
0x14002bc76  mov     r13d, [rbp+arg_8]
0x14002bc7a  mov     rax, [r14]
0x14002bc7d  mov     ecx, r13d
0x14002bc80  imul    ecx, [rdi+8]
0x14002bc84  cmp     [rcx+rdi+18h], rax
0x14002bc89  jz      short loc_14002BC98
0x14002bc8b  mov     edx, [rcx+rdi+20h]
0x14002bc8f  add     rdx, rsi
0x14002bc92  mov     r15d, [rdx+8]
0x14002bc96  jmp     short loc_14002BC9F
0x14002bc98  mov     rdx, [rbp+P]; Src
0x14002bc9c  mov     r15d, r12d
0x14002bc9f  mov     [rcx+rdi+20h], ebx
0x14002bca3  mov     [rcx+rdi+24h], r15d
0x14002bca8  mov     ecx, ebx
0x14002bcaa  add     rcx, rdi; void *
0x14002bcad  mov     r8d, r15d; Size
0x14002bcb0  call    memmove
0x14002bcb5  add     ebx, r15d
0x14002bcb8  inc     r13d
0x14002bcbb  cmp     r13d, [rdi+0Ch]
0x14002bcbf  jb      short loc_14002BC7A
0x14002bcc1  mov     r13, [rbp+arg_0]
0x14002bcc5  mov     r15, [rbp+var_8]
0x14002bcc9  cmp     ebx, 200000h
0x14002bccf  jbe     short loc_14002BCDB
0x14002bcd1  mov     ebx, 0C0000427h
0x14002bcd6  jmp     loc_14002BC3C
0x14002bcdb  mov     r8, [rbp+Object]
0x14002bcdf  mov     r9, rdi
0x14002bce2  mov     rdx, [rbp+FileHandle]
0x14002bce6  mov     rcx, r13
0x14002bce9  mov     dword ptr [rsp+60h+var_40], ebx
0x14002bced  call    WimWriteOverlayConfig
0x14002bcf2  xor     r12d, r12d
0x14002bcf5  mov     ebx, eax
0x14002bcf7  mov     [rbp+FileHandle], r12
0x14002bcfb  mov     [rbp+Object], r12
0x14002bcff  test    eax, eax
0x14002bd01  jns     short loc_14002BD23
0x14002bd03  mov     rcx, cs:WPP_GLOBAL_Control
0x14002bd0a  test    dword ptr [rcx+2Ch], 400h
0x14002bd11  jz      short loc_14002BD5B
0x14002bd13  cmp     byte ptr [rcx+29h], 2
0x14002bd17  jb      short loc_14002BD5B
0x14002bd19  lea     edx, [r12+36h]
0x14002bd1e  jmp     loc_14002BB89
0x14002bd23  call    WimPublishConfigChangeNotification
0x14002bd28  jmp     short loc_14002BD5B
0x14002bd2a  mov     rcx, cs:WPP_GLOBAL_Control
0x14002bd31  test    dword ptr [rcx+2Ch], 400h
0x14002bd38  jz      short loc_14002BD56
0x14002bd3a  cmp     byte ptr [rcx+29h], 2
0x14002bd3e  jb      short loc_14002BD56
0x14002bd40  mov     r9, [r14]
0x14002bd43  mov     rcx, [rcx+18h]
0x14002bd47  mov     [rsp+60h+var_38], r8
0x14002bd4c  mov     [rsp+60h+var_40], rdx
0x14002bd51  call    WPP_SF_i_guid__guid_
0x14002bd56  mov     ebx, 0C000000Dh
0x14002bd5b  test    rsi, rsi
0x14002bd5e  jz      short loc_14002BD71
0x14002bd60  xor     edx, edx; Tag
0x14002bd62  mov     rcx, rsi; P
0x14002bd65  call    cs:__imp_ExFreePoolWithTag
0x14002bd6c  nop     dword ptr [rax+rax+00h]
0x14002bd71  test    rdi, rdi
0x14002bd74  jz      short loc_14002BD87
0x14002bd76  xor     edx, edx; Tag
0x14002bd78  mov     rcx, rdi; P
0x14002bd7b  call    cs:__imp_ExFreePoolWithTag
0x14002bd82  nop     dword ptr [rax+rax+00h]
0x14002bd87  cmp     [rbp+P], r12
0x14002bd8b  jz      short loc_14002BD9F
0x14002bd8d  mov     rcx, [rbp+P]; P
0x14002bd91  xor     edx, edx; Tag
0x14002bd93  call    cs:__imp_ExFreePoolWithTag
0x14002bd9a  nop     dword ptr [rax+rax+00h]
0x14002bd9f  mov     rcx, [rbp+Object]; Object
0x14002bda3  test    rcx, rcx
0x14002bda6  jz      short loc_14002BDB4
0x14002bda8  call    cs:__imp_ObfDereferenceObject
0x14002bdaf  nop     dword ptr [rax+rax+00h]
0x14002bdb4  mov     rcx, [rbp+FileHandle]; FileHandle
0x14002bdb8  test    rcx, rcx
0x14002bdbb  jz      short loc_14002BDC9
0x14002bdbd  call    cs:__imp_FltClose
0x14002bdc4  nop     dword ptr [rax+rax+00h]
0x14002bdc9  mov     eax, ebx
0x14002bdcb  mov     rbx, [rsp+60h+arg_10]
0x14002bdd3  add     rsp, 60h
0x14002bdd7  pop     r15
0x14002bdd9  pop     r14
0x14002bddb  pop     r13
0x14002bddd  pop     r12
0x14002bddf  pop     rdi
0x14002bde0  pop     rsi
0x14002bde1  pop     rbp
0x14002bde2  retn
```
