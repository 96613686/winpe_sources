# WldpIsClassInApprovedList

- ea: `0x1800289a0`
- end: `0x180029034`
- name: `WldpIsClassInApprovedList`
- size: `1684`
- prototype: `__int64 __fastcall(struct _GUID *, _DWORD *, int *, int)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180001008`
- `0x180014eb0`
- `0x18001d1f0`
- `0x180021ec0`
- `0x1800229ec`
- `0x180027318`
- `0x1800289a0`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x180028fb1`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x180028fb1`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x180028f8d`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x180028f8d`
- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x180028ff3`
- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x180028ff3`
- `ntdll!RtlInitUnicodeString` at `0x180028dcb`
- `ntdll!RtlInitUnicodeString` at `0x180028ddc`
- `ntdll!RtlInitUnicodeString` at `0x180028ded`
- `ntdll!RtlInitUnicodeString` at `0x180028dcb`
- `ntdll!RtlInitUnicodeString` at `0x180028ddc`
- `ntdll!RtlInitUnicodeString` at `0x180028ded`
- `ntdll!RtlStringFromGUIDEx` at `0x180028ae9`
- `ntdll!RtlStringFromGUIDEx` at `0x180028ae9`
- `ntdll!NtQuerySecurityPolicy` at `0x180028b1e`
- `ntdll!NtQuerySecurityPolicy` at `0x180028b60`
- `ntdll!NtQuerySecurityPolicy` at `0x180028c0b`
- `ntdll!NtQuerySecurityPolicy` at `0x180028d63`
- `ntdll!NtQuerySecurityPolicy` at `0x180028e20`
- `ntdll!NtQuerySecurityPolicy` at `0x180028b1e`
- `ntdll!NtQuerySecurityPolicy` at `0x180028b60`
- `ntdll!NtQuerySecurityPolicy` at `0x180028c0b`
- `ntdll!NtQuerySecurityPolicy` at `0x180028d63`
- `ntdll!NtQuerySecurityPolicy` at `0x180028e20`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180028cbb`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180028cbb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180029002`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180029002`

## string_xrefs

- `0x180028dd1`: `ALLOWCLSIDS`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall WldpIsClassInApprovedList(struct _GUID *a1, _DWORD *a2, int *a3, int a4)
{
  struct _GUID v4; // xmm0
  __int64 v5; // r14
  __int64 *v6; // r12
  unsigned int v7; // ebx
  __int64 *v8; // r14
  __int64 *v11; // r15
  HRESULT v12; // edi
  int v13; // edx
  int v14; // eax
  int v15; // eax
  const wchar_t *v16; // rbx
  void *v17; // rbx
  int v18; // eax
  int v19; // ecx
  int v20; // r8d
  int v21; // r9d
  signed __int64 v22; // rbx
  _BYTE v24[4]; // [rsp+60h] [rbp-A0h] BYREF
  int v25; // [rsp+64h] [rbp-9Ch] BYREF
  int v26; // [rsp+68h] [rbp-98h] BYREF
  ULONGLONG RegHandle; // [rsp+70h] [rbp-90h] BYREF
  int v28; // [rsp+78h] [rbp-88h] BYREF
  LPOLESTR lpsz; // [rsp+80h] [rbp-80h] BYREF
  void *Buf1; // [rsp+88h] [rbp-78h] BYREF
  _QWORD v31[2]; // [rsp+90h] [rbp-70h] BYREF
  __int64 *v32; // [rsp+A0h] [rbp-60h] BYREF
  __int64 *v33; // [rsp+A8h] [rbp-58h] BYREF
  struct _GUID *p_Buf2; // [rsp+B0h] [rbp-50h] BYREF
  const wchar_t *v35; // [rsp+B8h] [rbp-48h] BYREF
  struct _UNICODE_STRING v36; // [rsp+C0h] [rbp-40h] BYREF
  struct _UNICODE_STRING v37; // [rsp+D0h] [rbp-30h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+E0h] [rbp-20h] BYREF
  struct _GUID Buf2; // [rsp+F0h] [rbp-10h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+100h] [rbp+0h] BYREF
  __int128 v41; // [rsp+110h] [rbp+10h]
  __int64 v42; // [rsp+120h] [rbp+20h]
  char v43; // [rsp+130h] [rbp+30h] BYREF

  v4 = *a1;
  v5 = (int)a2[1];
  v6 = &qword_180043A40;
  Buf1 = a1;
  v7 = 0;
  v42 = 0;
  v8 = &qword_180043990[2 * v5];
  LODWORD(RegHandle) = a4;
  Buf2 = v4;
  lpsz = 0;
  v24[0] = 0;
  v31[0] = 5111808;
  v26 = 1;
  v31[1] = &v43;
  v25 = 0;
  v11 = &qword_180043A10;
  DestinationString = 0;
  v37 = 0;
  v36 = 0;
  UserData = 0;
  v41 = 0;
  GetStateInfo(&UserData);
  if ( !a3 || *a2 != 1 || (unsigned int)(a2[1] - 2) > 3 )
  {
    v16 = L"&(";
LABEL_53:
    v12 = -2147024809;
    goto LABEL_54;
  }
  *a3 = 0;
  v12 = 0;
  v13 = *((_DWORD *)&UserData.Ptr + (int)a2[1]);
  if ( (v13 & 0x80000004) == 0x80000000
    || (v28 = 0, (v13 & 0x8000001C) == -2147483620 || (v13 & 0x80000007) == -2147483641) )
  {
    *a3 = 1;
    v16 = (const wchar_t *)&qword_180043A90;
    goto LABEL_54;
  }
  while ( 1 )
  {
    if ( (*((_DWORD *)&UserData.Ptr + (int)a2[1]) & 0x80000005) != 0x80000005 )
      goto LABEL_10;
    v6 = (__int64 *)L",.";
    v14 = RtlStringFromGUIDEx(&Buf2, v31, 0);
    if ( v14 < 0 )
      break;
    if ( (int)NtQuerySecurityPolicy(v8, v31, L",.", &v25, v24, &v26) >= 0 && !v25 )
    {
      v16 = L",.";
      *a3 = v24[0] != 0;
      goto LABEL_48;
    }
LABEL_10:
    if ( (int)NtQuerySecurityPolicy(&qword_1800439A0, &qword_180043A20, &qword_180043A60, &v25, v24, &v26) < 0
      || v25
      || !v24[0] )
    {
      v8 = &qword_1800439A0;
      v11 = &qword_180043A20;
      v6 = &qword_180043A60;
      while ( memcmp_0(&qword_180049D20[2 * v7], &Buf2, 0x10u) )
      {
        if ( ++v7 >= 0xC )
        {
          v7 = 0;
          goto LABEL_17;
        }
      }
      *a3 = 1;
      v16 = L"\"$";
      goto LABEL_54;
    }
LABEL_17:
    v15 = a2[1];
    v24[0] = 0;
    v26 = 1;
    if ( v15 != 2 )
    {
      if ( v15 == 3 )
      {
        if ( (int)NtQuerySecurityPolicy(&qword_1800439C0, &qword_180043A20, &qword_180043A60, &v25, v24, &v26) < 0
          || v25
          || !v24[0] )
        {
          v8 = &qword_1800439C0;
          v11 = &qword_180043A20;
          v6 = &qword_180043A60;
          while ( memcmp_0(&qword_180049970[2 * v7], &Buf2, 0x10u) )
          {
            if ( ++v7 >= 0x3B )
              goto LABEL_25;
          }
LABEL_45:
          *a3 = 1;
          v16 = L"&(";
          goto LABEL_54;
        }
LABEL_25:
        v24[0] = 0;
        v26 = 1;
        goto LABEL_26;
      }
      if ( v15 == 5 )
      {
        if ( (int)NtQuerySecurityPolicy(&qword_1800439E0, &qword_180043A20, &qword_180043A60, &v25, v24, &v26) < 0
          || v25
          || !v24[0] )
        {
          v8 = &qword_1800439E0;
          v11 = &qword_180043A20;
          v6 = &qword_180043A60;
          while ( memcmp_0(&qword_180049DE0[2 * v7], &Buf2, 0x10u) )
          {
            if ( ++v7 >= 2 )
            {
              RtlInitUnicodeString(&DestinationString, L"IE");
              RtlInitUnicodeString(&v37, L"ALLOWCLSIDS");
              RtlInitUnicodeString(&v36, L"ALL");
              v26 = 1;
              if ( (int)NtQuerySecurityPolicy(&DestinationString, &v37, &v36, &v25, v24, &v26) < 0
                || v25
                || v26 != 1
                || !v24[0] )
              {
                goto LABEL_25;
              }
              goto LABEL_45;
            }
          }
          goto LABEL_45;
        }
        goto LABEL_25;
      }
    }
LABEL_26:
    v6 = &qword_180043A40;
    v11 = &qword_180043A10;
    v8 = &qword_180043990[2 * a2[1]];
    if ( (*((_DWORD *)&UserData.Ptr + (int)a2[1]) & 0x8000001C) != 0x80000004 && (RegHandle & 2) == 0 )
    {
      v16 = L" \"";
      v12 = StringFromCLSID(&Buf2, &lpsz);
      if ( v12 < 0 )
        goto LABEL_54;
      if ( !lpsz )
        goto LABEL_53;
    }
    if ( v28
      || (v17 = Buf1, (int)ConfiguredClsidToReferenceClsid((GUID *)Buf1, &Buf2) < 0)
      || (v18 = memcmp_0(v17, &Buf2, 0x10u), v7 = 0, !v18) )
    {
      v16 = (const wchar_t *)&qword_180043AF0;
      goto LABEL_54;
    }
    v28 = 1;
  }
  v16 = L"@B";
  v12 = v14 | 0x10000000;
LABEL_48:
  v11 = &qword_180043A10;
LABEL_54:
  if ( (unsigned int)dword_18005A280 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18005A280, 0x200000000000LL) )
  {
    v28 = *a3;
    p_Buf2 = &Buf2;
    LODWORD(RegHandle) = v12;
    Buf1 = v6;
    v32 = v11;
    v33 = v8;
    v35 = v16;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapBuffer<_UNICODE_STRING>,_tlgWrapperByRef<16>,_tlgWrapBuffer<_UNICODE_STRING>,_tlgWrapBuffer<_UNICODE_STRING>,_tlgWrapBuffer<_UNICODE_STRING>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v19,
      (unsigned int)byte_18004EEE9,
      v20,
      v21,
      (__int64)&v35,
      (__int64)&p_Buf2,
      (__int64)&v33,
      (__int64)&v32,
      (__int64)&Buf1,
      (__int64)&v28,
      (__int64)&RegHandle);
  }
  if ( !*a3 )
  {
    v22 = _InterlockedCompareExchange64((volatile signed __int64 *)&g_ConfigCiEventHandle, 0, 0);
    RegHandle = v22;
    if ( v22 )
      goto LABEL_63;
    if ( !EventRegister(&SrpEventProviderId, 0, 0, &RegHandle) )
    {
      v22 = _InterlockedCompareExchange64((volatile signed __int64 *)&g_ConfigCiEventHandle, RegHandle, 0);
      if ( v22 )
      {
        EventUnregister(RegHandle);
        RegHandle = v22;
      }
      else
      {
        v22 = RegHandle;
      }
LABEL_63:
      UserData.Ptr = (ULONGLONG)a3;
      *(_QWORD *)&v41 = &Buf2;
      *(_QWORD *)&UserData.Size = 4;
      *((_QWORD *)&v41 + 1) = 16;
      EventWrite(v22, &WldpIsClassInApprovedListFail, 2u, &UserData);
    }
  }
  if ( lpsz )
    CoTaskMemFree(lpsz);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x1800289a0  mov     [rsp-8+arg_18], rbx
0x1800289a5  push    rbp
0x1800289a6  push    rsi
0x1800289a7  push    rdi
0x1800289a8  push    r12
0x1800289aa  push    r13
0x1800289ac  push    r14
0x1800289ae  push    r15
0x1800289b0  lea     rbp, [rsp-90h]
0x1800289b8  sub     rsp, 190h
0x1800289bf  mov     rax, cs:__security_cookie
0x1800289c6  xor     rax, rsp
0x1800289c9  mov     [rbp+0C0h+var_40], rax
0x1800289d0  movups  xmm0, xmmword ptr [rcx]
0x1800289d3  movsxd  r14, dword ptr [rdx+4]
0x1800289d7  lea     r12, qword_180043A40
0x1800289de  xor     eax, eax
0x1800289e0  mov     [rbp+0C0h+Buf1], rcx
0x1800289e4  xor     ebx, ebx
0x1800289e6  mov     [rbp+0C0h+var_A0], rax
0x1800289ea  lea     rax, qword_180043990
0x1800289f1  shl     r14, 4
0x1800289f5  add     r14, rax
0x1800289f8  mov     dword ptr [rsp+1C0h+RegHandle], r9d
0x1800289fd  movdqu  [rbp+0C0h+Buf2], xmm0
0x180028a02  mov     [rbp+0C0h+lpsz], rbx
0x180028a06  lea     eax, [rbx+4Eh]
0x180028a09  xorps   xmm0, xmm0
0x180028a0c  mov     [rsp+1C0h+var_160], bl
0x180028a10  movups  [rbp+0C0h+var_130], xmm0
0x180028a14  mov     word ptr [rbp+0C0h+var_130+2], ax
0x180028a18  lea     rcx, [rbp+0C0h+UserData]
0x180028a1c  lea     rax, [rbp+0C0h+var_90]
0x180028a20  mov     [rsp+1C0h+var_158], 1
0x180028a28  xorps   xmm1, xmm1
0x180028a2b  mov     qword ptr [rbp+0C0h+var_130+8], rax
0x180028a2f  mov     rsi, r8
0x180028a32  mov     [rsp+1C0h+var_15C], ebx
0x180028a36  mov     r13, rdx
0x180028a39  lea     r15, qword_180043A10
0x180028a40  movups  xmmword ptr [rbp+0C0h+DestinationString.Length], xmm0
0x180028a44  movups  xmmword ptr [rbp+0C0h+var_F0.Length], xmm1
0x180028a48  movups  xmmword ptr [rbp+0C0h+var_100.Length], xmm0
0x180028a4c  movups  xmmword ptr [rbp+0C0h+UserData.Ptr], xmm0
0x180028a50  movups  [rbp+0C0h+var_B0], xmm0
0x180028a54  call    GetStateInfo
0x180028a59  test    rsi, rsi
0x180028a5c  jz      loc_180028EAF
0x180028a62  cmp     dword ptr [r13+0], 1
0x180028a67  jnz     loc_180028EAF
0x180028a6d  mov     eax, [r13+4]
0x180028a71  sub     eax, 2
0x180028a74  cmp     eax, 3
0x180028a77  ja      loc_180028EAF
0x180028a7d  mov     [rsi], ebx
0x180028a7f  mov     edi, ebx
0x180028a81  movsxd  rax, dword ptr [r13+4]
0x180028a85  mov     edx, dword ptr [rbp+rax*4+0C0h+UserData.Ptr]
0x180028a89  mov     eax, edx
0x180028a8b  and     eax, 80000004h
0x180028a90  cmp     eax, 80000000h
0x180028a95  jz      loc_180028EA0
0x180028a9b  mov     ecx, 8000001Ch
0x180028aa0  mov     [rsp+1C0h+var_148], ebx
0x180028aa4  mov     eax, edx
0x180028aa6  and     eax, ecx
0x180028aa8  cmp     eax, ecx
0x180028aaa  mov     eax, 80000007h
0x180028aaf  setnz   cl
0x180028ab2  and     edx, eax
0x180028ab4  cmp     edx, eax
0x180028ab6  setnz   al
0x180028ab9  test    al, cl
0x180028abb  jz      loc_180028EA0
0x180028ac1  movsxd  rax, dword ptr [r13+4]
0x180028ac5  mov     ecx, dword ptr [rbp+rax*4+0C0h+UserData.Ptr]
0x180028ac9  and     ecx, 80000005h
0x180028acf  cmp     ecx, 80000005h
0x180028ad5  jnz     short loc_180028B32
0x180028ad7  xor     r8d, r8d
0x180028ada  lea     rdx, [rbp+0C0h+var_130]
0x180028ade  lea     rcx, [rbp+0C0h+Buf2]
0x180028ae2  lea     r12, asc_180043A50; ",."
0x180028ae9  call    cs:__imp_RtlStringFromGUIDEx
0x180028aef  test    eax, eax
0x180028af1  js      loc_180028E72
0x180028af7  lea     rax, [rsp+1C0h+var_158]
0x180028afc  mov     rcx, r14
0x180028aff  mov     [rsp+1C0h+var_198], rax
0x180028b04  lea     r9, [rsp+1C0h+var_15C]
0x180028b09  lea     rax, [rsp+1C0h+var_160]
0x180028b0e  lea     r8, asc_180043A50; ",."
0x180028b15  mov     [rsp+1C0h+var_1A0], rax
0x180028b1a  lea     rdx, [rbp+0C0h+var_130]
0x180028b1e  call    cs:__imp_NtQuerySecurityPolicy
0x180028b24  test    eax, eax
0x180028b26  js      short loc_180028B32
0x180028b28  cmp     [rsp+1C0h+var_15C], ebx
0x180028b2c  jz      loc_180028E5E
0x180028b32  lea     rax, [rsp+1C0h+var_158]
0x180028b37  mov     [rsp+1C0h+var_198], rax
0x180028b3c  lea     r9, [rsp+1C0h+var_15C]
0x180028b41  lea     rax, [rsp+1C0h+var_160]
0x180028b46  lea     r8, qword_180043A60
0x180028b4d  mov     [rsp+1C0h+var_1A0], rax
0x180028b52  lea     rdx, qword_180043A20
0x180028b59  lea     rcx, qword_1800439A0
0x180028b60  call    cs:__imp_NtQuerySecurityPolicy
0x180028b66  test    eax, eax
0x180028b68  js      short loc_180028B76
0x180028b6a  cmp     [rsp+1C0h+var_15C], ebx
0x180028b6e  jnz     short loc_180028B76
0x180028b70  cmp     [rsp+1C0h+var_160], bl
0x180028b74  jnz     short loc_180028BBB
0x180028b76  lea     r14, qword_1800439A0
0x180028b7d  lea     r15, qword_180043A20
0x180028b84  lea     r12, qword_180043A60
0x180028b8b  lea     rax, qword_180049D20
0x180028b92  mov     ecx, ebx
0x180028b94  shl     rcx, 4
0x180028b98  lea     rdx, [rbp+0C0h+Buf2]; Buf2
0x180028b9c  add     rcx, rax; Buf1
0x180028b9f  mov     r8d, 10h; Size
0x180028ba5  call    memcmp_0
0x180028baa  test    eax, eax
0x180028bac  jz      loc_180028E91
0x180028bb2  inc     ebx
0x180028bb4  cmp     ebx, 0Ch
0x180028bb7  jb      short loc_180028B8B
0x180028bb9  xor     ebx, ebx
0x180028bbb  mov     eax, [r13+4]
0x180028bbf  mov     [rsp+1C0h+var_160], bl
0x180028bc3  mov     [rsp+1C0h+var_158], 1
0x180028bcb  cmp     eax, 2
0x180028bce  jz      loc_180028C72
0x180028bd4  cmp     eax, 3
0x180028bd7  jnz     loc_180028D23
0x180028bdd  lea     rax, [rsp+1C0h+var_158]
0x180028be2  mov     [rsp+1C0h+var_198], rax
0x180028be7  lea     r9, [rsp+1C0h+var_15C]
0x180028bec  lea     rax, [rsp+1C0h+var_160]
0x180028bf1  lea     r8, qword_180043A60
0x180028bf8  mov     [rsp+1C0h+var_1A0], rax
0x180028bfd  lea     rdx, qword_180043A20
0x180028c04  lea     rcx, qword_1800439C0
0x180028c0b  call    cs:__imp_NtQuerySecurityPolicy
0x180028c11  test    eax, eax
0x180028c13  js      short loc_180028C21
0x180028c15  cmp     [rsp+1C0h+var_15C], ebx
0x180028c19  jnz     short loc_180028C21
0x180028c1b  cmp     [rsp+1C0h+var_160], bl
0x180028c1f  jnz     short loc_180028C66
0x180028c21  lea     r14, qword_1800439C0
0x180028c28  lea     r15, qword_180043A20
0x180028c2f  lea     r12, qword_180043A60
0x180028c36  lea     rax, qword_180049970
0x180028c3d  mov     ecx, ebx
0x180028c3f  shl     rcx, 4
0x180028c43  lea     rdx, [rbp+0C0h+Buf2]; Buf2
0x180028c47  add     rcx, rax; Buf1
0x180028c4a  mov     r8d, 10h; Size
0x180028c50  call    memcmp_0
0x180028c55  test    eax, eax
0x180028c57  jz      loc_180028E4F
0x180028c5d  inc     ebx
0x180028c5f  cmp     ebx, 3Bh ; ';'
0x180028c62  jb      short loc_180028C36
0x180028c64  xor     ebx, ebx
0x180028c66  mov     [rsp+1C0h+var_160], bl
0x180028c6a  mov     [rsp+1C0h+var_158], 1
0x180028c72  movsxd  rax, dword ptr [r13+4]
0x180028c76  lea     rcx, qword_180043990
0x180028c7d  mov     r14, rax
0x180028c80  lea     r12, qword_180043A40
0x180028c87  shl     r14, 4
0x180028c8b  lea     r15, qword_180043A10
0x180028c92  add     r14, rcx
0x180028c95  mov     eax, dword ptr [rbp+rax*4+0C0h+UserData.Ptr]
0x180028c99  and     eax, 8000001Ch
0x180028c9e  cmp     eax, 80000004h
0x180028ca3  jz      short loc_180028CD8
0x180028ca5  test    byte ptr [rsp+1C0h+RegHandle], 2
0x180028caa  jnz     short loc_180028CD8
0x180028cac  lea     rdx, [rbp+0C0h+lpsz]; lplpsz
0x180028cb0  lea     rcx, [rbp+0C0h+Buf2]; rclsid
0x180028cb4  lea     rbx, asc_180043AE0; " \""
0x180028cbb  call    cs:__imp_StringFromCLSID
0x180028cc1  mov     edi, eax
0x180028cc3  test    eax, eax
0x180028cc5  js      loc_180028EBB
0x180028ccb  cmp     [rbp+0C0h+lpsz], 0
0x180028cd0  jz      loc_180028EB6
0x180028cd6  xor     ebx, ebx
0x180028cd8  cmp     [rsp+1C0h+var_148], ebx
0x180028cdc  jnz     loc_180028E88
0x180028ce2  mov     rbx, [rbp+0C0h+Buf1]
0x180028ce6  lea     rdx, [rbp+0C0h+Buf2]; struct _GUID *
0x180028cea  mov     rcx, rbx; guid
0x180028ced  call    ?ConfiguredClsidToReferenceClsid@@YAJAEBU_GUID@@PEAU1@@Z; ConfiguredClsidToReferenceClsid(_GUID const &,_GUID *)
0x180028cf2  test    eax, eax
0x180028cf4  js      loc_180028E88
0x180028cfa  mov     r8d, 10h; Size
0x180028d00  lea     rdx, [rbp+0C0h+Buf2]; Buf2
0x180028d04  mov     rcx, rbx; Buf1
0x180028d07  call    memcmp_0
0x180028d0c  xor     ebx, ebx
0x180028d0e  test    eax, eax
0x180028d10  jz      loc_180028E88
0x180028d16  mov     [rsp+1C0h+var_148], 1
0x180028d1e  jmp     loc_180028AC1
0x180028d23  cmp     eax, 4
0x180028d26  jz      loc_180028C72
0x180028d2c  cmp     eax, 5
0x180028d2f  jnz     loc_180028C72
0x180028d35  lea     rax, [rsp+1C0h+var_158]
0x180028d3a  mov     [rsp+1C0h+var_198], rax
0x180028d3f  lea     r9, [rsp+1C0h+var_15C]
0x180028d44  lea     rax, [rsp+1C0h+var_160]
0x180028d49  lea     r8, qword_180043A60
0x180028d50  mov     [rsp+1C0h+var_1A0], rax
0x180028d55  lea     rdx, qword_180043A20
0x180028d5c  lea     rcx, qword_1800439E0
0x180028d63  call    cs:__imp_NtQuerySecurityPolicy
0x180028d69  test    eax, eax
0x180028d6b  js      short loc_180028D7D
0x180028d6d  cmp     [rsp+1C0h+var_15C], ebx
0x180028d71  jnz     short loc_180028D7D
0x180028d73  cmp     [rsp+1C0h+var_160], bl
0x180028d77  jnz     loc_180028C66
0x180028d7d  lea     r14, qword_1800439E0
0x180028d84  lea     r15, qword_180043A20
0x180028d8b  lea     r12, qword_180043A60
0x180028d92  lea     rax, qword_180049DE0
0x180028d99  mov     ecx, ebx
0x180028d9b  shl     rcx, 4
0x180028d9f  lea     rdx, [rbp+0C0h+Buf2]; Buf2
0x180028da3  add     rcx, rax; Buf1
0x180028da6  mov     r8d, 10h; Size
0x180028dac  call    memcmp_0
0x180028db1  test    eax, eax
0x180028db3  jz      loc_180028E4F
0x180028db9  inc     ebx
0x180028dbb  cmp     ebx, 2
0x180028dbe  jb      short loc_180028D92
0x180028dc0  lea     rdx, SourceString; "IE"
0x180028dc7  lea     rcx, [rbp+0C0h+DestinationString]; DestinationString
0x180028dcb  call    cs:__imp_RtlInitUnicodeString
0x180028dd1  lea     rdx, aAllowclsids; "ALLOWCLSIDS"
0x180028dd8  lea     rcx, [rbp+0C0h+var_F0]; DestinationString
0x180028ddc  call    cs:__imp_RtlInitUnicodeString
0x180028de2  lea     rdx, aAll; "ALL"
0x180028de9  lea     rcx, [rbp+0C0h+var_100]; DestinationString
0x180028ded  call    cs:__imp_RtlInitUnicodeString
0x180028df3  lea     rax, [rsp+1C0h+var_158]
0x180028df8  mov     [rsp+1C0h+var_158], 1
0x180028e00  mov     [rsp+1C0h+var_198], rax
0x180028e05  lea     r9, [rsp+1C0h+var_15C]
0x180028e0a  lea     rax, [rsp+1C0h+var_160]
0x180028e0f  lea     r8, [rbp+0C0h+var_100]
0x180028e13  mov     [rsp+1C0h+var_1A0], rax
0x180028e18  lea     rdx, [rbp+0C0h+var_F0]
0x180028e1c  lea     rcx, [rbp+0C0h+DestinationString]
0x180028e20  call    cs:__imp_NtQuerySecurityPolicy
0x180028e26  xor     ebx, ebx
0x180028e28  test    eax, eax
0x180028e2a  js      loc_180028C66
0x180028e30  cmp     [rsp+1C0h+var_15C], ebx
0x180028e34  jnz     loc_180028C66
0x180028e3a  cmp     [rsp+1C0h+var_158], 1
0x180028e3f  jnz     loc_180028C66
0x180028e45  cmp     [rsp+1C0h+var_160], bl
0x180028e49  jz      loc_180028C66
0x180028e4f  mov     dword ptr [rsi], 1
0x180028e55  lea     rbx, asc_180043AD0; "&("
0x180028e5c  jmp     short loc_180028EBB
0x180028e5e  xor     eax, eax
0x180028e60  lea     rbx, asc_180043AB0; ",."
0x180028e67  cmp     [rsp+1C0h+var_160], al
0x180028e6b  setnz   al
0x180028e6e  mov     [rsi], eax
0x180028e70  jmp     short loc_180028E7F
0x180028e72  mov     edi, eax
0x180028e74  lea     rbx, aB; "@B"
0x180028e7b  bts     edi, 1Ch
0x180028e7f  lea     r15, qword_180043A10
0x180028e86  jmp     short loc_180028EBB
0x180028e88  lea     rbx, qword_180043AF0
0x180028e8f  jmp     short loc_180028EBB
0x180028e91  mov     dword ptr [rsi], 1
0x180028e97  lea     rbx, asc_180043AC0; "\"$"
0x180028e9e  jmp     short loc_180028EBB
0x180028ea0  mov     dword ptr [rsi], 1
0x180028ea6  lea     rbx, qword_180043A90
0x180028ead  jmp     short loc_180028EBB
0x180028eaf  lea     rbx, asc_180043A80; "&("
0x180028eb6  mov     edi, 80070057h
0x180028ebb  mov     eax, cs:dword_18005A280
0x180028ec1  cmp     eax, 5
0x180028ec4  jbe     loc_180028F53
0x180028eca  mov     rdx, 200000000000h
  ... truncated ...
```
