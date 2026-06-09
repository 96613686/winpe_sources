# WTLogConfigCiSignerEvent

- ea: `0x180043b10`
- end: `0x180043da4`
- name: `WTLogConfigCiSignerEvent`
- size: `660`
- prototype: `__int64 __fastcall(struct _CRYPT_PROVIDER_DATA *, LPCGUID ActivityId)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config`

## callees

- `0x1800246f0`
- `0x18002627c`
- `0x18002640c`
- `0x180043b10`
- `0x18004de6a`
- `0x18004deb0`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180043d65`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180043d65`

## pseudocode

```c
__int64 __fastcall WTLogConfigCiSignerEvent(struct _CRYPT_PROVIDER_DATA *a1, LPCGUID ActivityId, int a3, int a4)
{
  int EventHandle; // ebx
  __int64 v8; // rdx
  const wchar_t *v9; // rax
  int v10; // ecx
  const wchar_t *v11; // rax
  int v12; // ecx
  _WORD v13[2]; // [rsp+30h] [rbp-D0h] BYREF
  _WORD v14[2]; // [rsp+34h] [rbp-CCh] BYREF
  int v15; // [rsp+38h] [rbp-C8h] BYREF
  REGHANDLE RegHandle[2]; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v17; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v18; // [rsp+60h] [rbp-A0h]
  __int128 v19; // [rsp+70h] [rbp-90h]
  __int64 v20; // [rsp+80h] [rbp-80h]
  __int64 v21; // [rsp+88h] [rbp-78h]
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+A0h] [rbp-60h] BYREF
  int *v23; // [rsp+B0h] [rbp-50h]
  __int64 v24; // [rsp+B8h] [rbp-48h]
  _WORD *v25; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v26; // [rsp+C8h] [rbp-38h]
  const wchar_t *v27; // [rsp+D0h] [rbp-30h]
  int v28; // [rsp+D8h] [rbp-28h]
  int v29; // [rsp+DCh] [rbp-24h]
  _WORD *v30; // [rsp+E0h] [rbp-20h]
  __int64 v31; // [rsp+E8h] [rbp-18h]
  const wchar_t *v32; // [rsp+F0h] [rbp-10h]
  int v33; // [rsp+F8h] [rbp-8h]
  int v34; // [rsp+FCh] [rbp-4h]
  int *v35; // [rsp+100h] [rbp+0h]
  __int64 v36; // [rsp+108h] [rbp+8h]
  __int64 v37; // [rsp+110h] [rbp+10h]
  int v38; // [rsp+118h] [rbp+18h]
  int v39; // [rsp+11Ch] [rbp+1Ch]
  int *v40; // [rsp+120h] [rbp+20h]
  __int64 v41; // [rsp+128h] [rbp+28h]
  __int64 v42; // [rsp+130h] [rbp+30h]
  int v43; // [rsp+138h] [rbp+38h]
  int v44; // [rsp+13Ch] [rbp+3Ch]
  int v45; // [rsp+1A0h] [rbp+A0h] BYREF
  int v46; // [rsp+1A8h] [rbp+A8h] BYREF

  v46 = a4;
  v45 = a3;
  v20 = 0;
  v21 = 0;
  RegHandle[0] = 0;
  v13[0] = 0;
  v14[0] = 0;
  v15 = 0;
  v17 = 0;
  LODWORD(v17) = 56;
  v18 = 0;
  v19 = 0;
  if ( a1 && ActivityId )
  {
    EventHandle = GetEventHandle(RegHandle);
    if ( EventHandle < 0
      || (EventHandle = SiChainInfo::ConvertFromProvData((SiChainInfo *)&v17, a1, 0, 0), EventHandle < 0) )
    {
      SiChainInfo::~SiChainInfo((SiChainInfo *)&v17);
      return (unsigned int)EventHandle;
    }
    else
    {
      memset_0(&v25, 0, 0x80u);
      UserData.Ptr = (ULONGLONG)&v45;
      v23 = &v46;
      *(_QWORD *)&UserData.Size = 4;
      v24 = 4;
      if ( (_DWORD)v19 )
      {
        v8 = *((_QWORD *)&v18 + 1) + 48LL;
        v13[0] = *(_WORD *)(*((_QWORD *)&v18 + 1) + 16LL) >> 1;
        v26 = 2;
        v25 = v13;
        if ( (unsigned int)v19 <= 1 )
          v8 = *((_QWORD *)&v18 + 1);
        v9 = *(const wchar_t **)(*((_QWORD *)&v18 + 1) + 24LL);
        v28 = *(unsigned __int16 *)(*((_QWORD *)&v18 + 1) + 16LL);
        v27 = v9;
        v35 = (int *)(*((_QWORD *)&v18 + 1) + 4LL);
        v29 = 0;
        v36 = 4;
        v10 = *(_DWORD *)(*((_QWORD *)&v18 + 1) + 4LL);
        v37 = *(_QWORD *)(*((_QWORD *)&v18 + 1) + 8LL);
        v38 = v10;
        v39 = 0;
        v14[0] = *(_WORD *)(v8 + 16) >> 1;
        v30 = v14;
        v31 = 2;
        v11 = *(const wchar_t **)(v8 + 24);
        v33 = *(unsigned __int16 *)(v8 + 16);
        v40 = (int *)(v8 + 4);
        v32 = v11;
        v34 = 0;
        v41 = 4;
        v12 = *(_DWORD *)(v8 + 4);
        v42 = *(_QWORD *)(v8 + 8);
        v43 = v12;
        v44 = 0;
      }
      else
      {
        v26 = 2;
        v14[0] = 7;
        v13[0] = 7;
        v25 = v13;
        v28 = 14;
        v33 = 14;
        v35 = &v15;
        v40 = &v15;
        v27 = L"Unknown";
        v29 = 0;
        v36 = 4;
        v30 = v14;
        v31 = 2;
        v32 = L"Unknown";
        v34 = 0;
        v41 = 4;
      }
      EventWriteTransfer(RegHandle[0], &WintrustImageVerification, ActivityId, 0, 0xAu, &UserData);
      SiChainInfo::~SiChainInfo((SiChainInfo *)&v17);
      return 0;
    }
  }
  else
  {
    SiChainInfo::~SiChainInfo((SiChainInfo *)&v17);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x180043b10  mov     [rsp-8+arg_18], r9d
0x180043b15  mov     [rsp-8+arg_10], r8d
0x180043b1a  push    rbp
0x180043b1b  push    rbx
0x180043b1c  push    rsi
0x180043b1d  push    rdi
0x180043b1e  push    r14
0x180043b20  push    r15
0x180043b22  lea     rbp, [rsp-58h]
0x180043b27  sub     rsp, 158h
0x180043b2e  mov     rax, cs:__security_cookie
0x180043b35  xor     rax, rsp
0x180043b38  mov     [rbp+80h+var_40], rax
0x180043b3c  xor     r14d, r14d
0x180043b3f  xor     eax, eax
0x180043b41  mov     [rbp+80h+var_100], rax
0x180043b45  xorps   xmm0, xmm0
0x180043b48  mov     [rbp+80h+var_F8], r14
0x180043b4c  mov     rdi, rdx
0x180043b4f  mov     [rsp+180h+RegHandle], r14
0x180043b54  mov     rsi, rcx
0x180043b57  mov     [rsp+180h+var_150], r14w
0x180043b5d  lea     r15d, [rax+0Eh]
0x180043b61  mov     [rsp+180h+var_14C], r14w
0x180043b67  mov     [rsp+180h+var_148], r14d
0x180043b6c  movups  [rsp+180h+var_130], xmm0
0x180043b71  mov     dword ptr [rsp+180h+var_130], 38h ; '8'
0x180043b79  movups  [rsp+180h+var_120], xmm0
0x180043b7e  movups  [rsp+180h+var_110], xmm0
0x180043b83  test    rcx, rcx
0x180043b86  jz      loc_180043D79
0x180043b8c  test    rdx, rdx
0x180043b8f  jz      loc_180043D79
0x180043b95  lea     rcx, [rsp+180h+RegHandle]; unsigned __int64 *
0x180043b9a  call    ?GetEventHandle@@YAJPEA_K@Z; GetEventHandle(unsigned __int64 *)
0x180043b9f  lea     rcx, [rsp+180h+var_130]; this
0x180043ba4  mov     ebx, eax
0x180043ba6  test    eax, eax
0x180043ba8  jns     short loc_180043BB6
0x180043baa  call    ??1SiChainInfo@@QEAA@XZ; SiChainInfo::~SiChainInfo(void)
0x180043baf  mov     eax, ebx
0x180043bb1  jmp     loc_180043D88
0x180043bb6  xor     r9d, r9d; unsigned __int8
0x180043bb9  xor     r8d, r8d; unsigned __int8
0x180043bbc  mov     rdx, rsi; struct _CRYPT_PROVIDER_DATA *
0x180043bbf  call    ?ConvertFromProvData@SiChainInfo@@QEAAJPEBU_CRYPT_PROVIDER_DATA@@EE@Z; SiChainInfo::ConvertFromProvData(_CRYPT_PROVIDER_DATA const *,uchar,uchar)
0x180043bc4  mov     ebx, eax
0x180043bc6  test    eax, eax
0x180043bc8  jns     short loc_180043BD1
0x180043bca  lea     rcx, [rsp+180h+var_130]
0x180043bcf  jmp     short loc_180043BAA
0x180043bd1  xor     edx, edx; Val
0x180043bd3  lea     rcx, [rbp+80h+var_C0]; void *
0x180043bd7  mov     r8d, 80h; Size
0x180043bdd  call    memset_0
0x180043be2  mov     r10d, dword ptr [rsp+180h+var_110]
0x180043be7  lea     rax, [rbp+80h+arg_10]
0x180043bee  mov     [rbp+80h+var_E0.Ptr], rax
0x180043bf2  lea     rax, [rbp+80h+arg_18]
0x180043bf9  mov     [rbp+80h+var_D0], rax
0x180043bfd  mov     qword ptr [rbp+80h+var_E0.Size], 4
0x180043c05  mov     [rbp+80h+var_C8], 4
0x180043c0d  test    r10d, r10d
0x180043c10  jz      loc_180043CCD
0x180043c16  mov     r8, qword ptr [rsp+180h+var_120+8]
0x180043c1b  movzx   eax, word ptr [r8+10h]
0x180043c20  lea     rdx, [r8+30h]
0x180043c24  shr     ax, 1
0x180043c27  mov     [rsp+180h+var_150], ax
0x180043c2c  cmp     r10d, 1
0x180043c30  mov     [rbp+80h+var_B8], 2
0x180043c38  lea     rax, [rsp+180h+var_150]
0x180043c3d  mov     [rbp+80h+var_C0], rax
0x180043c41  cmovbe  rdx, r8
0x180043c45  movzx   ecx, word ptr [r8+10h]
0x180043c4a  mov     rax, [r8+18h]
0x180043c4e  mov     [rbp+80h+var_A8], ecx
0x180043c51  lea     rcx, [r8+4]
0x180043c55  mov     [rbp+80h+var_B0], rax
0x180043c59  mov     [rbp+80h+var_80], rcx
0x180043c5d  mov     [rbp+80h+var_A4], r14d
0x180043c61  mov     [rbp+80h+var_78], 4
0x180043c69  mov     ecx, [rcx]
0x180043c6b  mov     rax, [r8+8]
0x180043c6f  mov     [rbp+80h+var_70], rax
0x180043c73  mov     [rbp+80h+var_68], ecx
0x180043c76  mov     [rbp+80h+var_64], r14d
0x180043c7a  movzx   eax, word ptr [rdx+10h]
0x180043c7e  shr     ax, 1
0x180043c81  mov     [rsp+180h+var_14C], ax
0x180043c86  lea     rax, [rsp+180h+var_14C]
0x180043c8b  mov     [rbp+80h+var_A0], rax
0x180043c8f  mov     [rbp+80h+var_98], 2
0x180043c97  movzx   ecx, word ptr [rdx+10h]
0x180043c9b  mov     rax, [rdx+18h]
0x180043c9f  mov     [rbp+80h+var_88], ecx
0x180043ca2  lea     rcx, [rdx+4]
0x180043ca6  mov     [rbp+80h+var_60], rcx
0x180043caa  mov     [rbp+80h+var_90], rax
0x180043cae  mov     [rbp+80h+var_84], r14d
0x180043cb2  mov     [rbp+80h+var_58], 4
0x180043cba  mov     rax, [rdx+8]
0x180043cbe  mov     ecx, [rcx]
0x180043cc0  mov     [rbp+80h+var_50], rax
0x180043cc4  mov     [rbp+80h+var_48], ecx
0x180043cc7  mov     [rbp+80h+var_44], r14d
0x180043ccb  jmp     short loc_180043D42
0x180043ccd  movzx   eax, r15w
0x180043cd1  mov     [rbp+80h+var_B8], 2
0x180043cd9  shr     ax, 1
0x180043cdc  lea     rcx, [rsp+180h+var_148]
0x180043ce1  mov     [rsp+180h+var_14C], ax
0x180043ce6  lea     rdx, aUnknown; "Unknown"
0x180043ced  mov     [rsp+180h+var_150], ax
0x180043cf2  lea     rax, [rsp+180h+var_150]
0x180043cf7  mov     [rbp+80h+var_C0], rax
0x180043cfb  mov     eax, r15d
0x180043cfe  mov     [rbp+80h+var_A8], eax
0x180043d01  mov     [rbp+80h+var_88], eax
0x180043d04  lea     rax, [rsp+180h+var_148]
0x180043d09  mov     [rbp+80h+var_80], rcx
0x180043d0d  lea     rcx, [rsp+180h+var_14C]
0x180043d12  mov     [rbp+80h+var_60], rax
0x180043d16  mov     [rbp+80h+var_B0], rdx
0x180043d1a  mov     [rbp+80h+var_A4], r14d
0x180043d1e  mov     [rbp+80h+var_78], 4
0x180043d26  mov     [rbp+80h+var_A0], rcx
0x180043d2a  mov     [rbp+80h+var_98], 2
0x180043d32  mov     [rbp+80h+var_90], rdx
0x180043d36  mov     [rbp+80h+var_84], r14d
0x180043d3a  mov     [rbp+80h+var_58], 4
0x180043d42  mov     rcx, [rsp+180h+RegHandle]; RegHandle
0x180043d47  lea     rax, [rbp+80h+var_E0]
0x180043d4b  mov     [rsp+180h+UserData], rax; UserData
0x180043d50  lea     rdx, WintrustImageVerification; EventDescriptor
0x180043d57  xor     r9d, r9d; RelatedActivityId
0x180043d5a  mov     [rsp+180h+UserDataCount], 0Ah; UserDataCount
0x180043d62  mov     r8, rdi; ActivityId
0x180043d65  call    cs:__imp_EventWriteTransfer
0x180043d6b  lea     rcx, [rsp+180h+var_130]; this
0x180043d70  call    ??1SiChainInfo@@QEAA@XZ; SiChainInfo::~SiChainInfo(void)
0x180043d75  xor     eax, eax
0x180043d77  jmp     short loc_180043D88
0x180043d79  lea     rcx, [rsp+180h+var_130]; this
0x180043d7e  call    ??1SiChainInfo@@QEAA@XZ; SiChainInfo::~SiChainInfo(void)
0x180043d83  mov     eax, 80070057h
0x180043d88  mov     rcx, [rbp+80h+var_40]
0x180043d8c  xor     rcx, rsp; StackCookie
0x180043d8f  call    __security_check_cookie
0x180043d94  add     rsp, 158h
0x180043d9b  pop     r15
0x180043d9d  pop     r14
0x180043d9f  pop     rdi
0x180043da0  pop     rsi
0x180043da1  pop     rbx
0x180043da2  pop     rbp
0x180043da3  retn
```
