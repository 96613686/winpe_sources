# VmbusPipeServerOfferChannelExInternal(_VMBUS_PIPE_SERVER_OFFER_EX const *,uint,uint,void * *)

- ea: `0x1800012b0`
- end: `0x1800017cc`
- name: `?VmbusPipeServerOfferChannelExInternal@@YAJPEBU_VMBUS_PIPE_SERVER_OFFER_EX@@IIPEAPEAX@Z`
- size: `1308`
- prototype: `int __fastcall(const struct _VMBUS_PIPE_SERVER_OFFER_EX *, unsigned int, int, void **)`
- caller_count: `2`
- callee_count: `14`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180001130`
- `0x180001160`

## callees

- `0x1800012b0`
- `0x1800017e0`
- `0x180001810`
- `0x180001b44`
- `0x180001f64`
- `0x1800024e0`
- `0x1800030ae`
- `0x180005d94`
- `0x180005db8`
- `0x180007578`
- `0x18000761c`
- `0x180007694`
- `0x180007774`
- `0x1800077a0`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x1800014f1`
- `ntdll!RtlInitUnicodeString` at `0x1800014f1`
- `ntdll!NtOpenFile` at `0x18000155e`
- `ntdll!NtOpenFile` at `0x18000155e`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180001724`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180001724`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180001747`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180001747`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180001600`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180001600`

## string_xrefs

- `0x1800013bb`: `onecore\vm\dv\vmbus\pipes\dll\server.cpp`
- `0x18000163f`: `onecore\vm\dv\vmbus\pipes\dll\server.cpp`
- `0x180001682`: `onecore\vm\dv\vmbus\pipes\dll\server.cpp`
- `0x1800016bc`: `onecore\vm\dv\vmbus\pipes\dll\server.cpp`
- `0x180001759`: `onecore\vm\dv\vmbus\pipes\dll\server.cpp`
- `0x180001784`: `onecore\vm\dv\vmbus\pipes\dll\server.cpp`
- `0x1800017b0`: `onecore\vm\dv\vmbus\pipes\dll\server.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
int __fastcall VmbusPipeServerOfferChannelExInternal(
        const struct _VMBUS_PIPE_SERVER_OFFER_EX *a1,
        unsigned int a2,
        int a3,
        void **a4)
{
  size_t v8; // r8
  HRESULT v9; // eax
  unsigned int v10; // r10d
  HRESULT v11; // eax
  unsigned __int64 v12; // rdx
  __int128 v14; // xmm0
  __int16 v15; // cx
  __int128 v16; // xmm1
  char v17; // al
  __int128 v18; // xmm0
  char v19; // al
  __int128 v20; // xmm1
  __int128 v21; // xmm0
  __int128 v22; // xmm1
  __int128 v23; // xmm0
  __int128 v24; // xmm1
  __int128 v25; // xmm0
  void *v26; // rbx
  unsigned __int16 *v27; // rdx
  NTSTATUS v28; // eax
  void *v29; // rdx
  unsigned int v30; // r8d
  int LastError; // edi
  const char *v32; // r9
  wil::details::in1diag3 *v33; // rcx
  __int64 v34; // r9
  __int64 v35; // rdx
  int v36; // eax
  void *v37; // rdx
  unsigned int v38; // r8d
  void *v39; // rdx
  unsigned int v40; // r8d
  const char *v41; // r9
  unsigned int cchToCopy; // [rsp+28h] [rbp-E0h]
  unsigned int cchToCopya; // [rsp+28h] [rbp-E0h]
  int cchToCopyb; // [rsp+28h] [rbp-E0h]
  int cchToCopyc; // [rsp+28h] [rbp-E0h]
  int cchToCopyd; // [rsp+28h] [rbp-E0h]
  unsigned int OpenOptions; // [rsp+30h] [rbp-D8h]
  size_t pcchNewDestLength; // [rsp+48h] [rbp-C0h] BYREF
  LPOLESTR lpsz; // [rsp+50h] [rbp-B8h] BYREF
  _QWORD ObjectAttributes[8]; // [rsp+58h] [rbp-B0h] BYREF
  __int64 InBuffer; // [rsp+98h] [rbp-70h] BYREF
  char v52; // [rsp+A0h] [rbp-68h]
  char v53; // [rsp+A1h] [rbp-67h]
  char v54; // [rsp+A2h] [rbp-66h]
  __int128 v55; // [rsp+A4h] [rbp-64h]
  __int128 v56; // [rsp+B4h] [rbp-54h]
  int v57; // [rsp+C4h] [rbp-44h]
  __int16 v58; // [rsp+C8h] [rbp-40h]
  __int16 v59; // [rsp+CAh] [rbp-3Eh]
  __int128 v60; // [rsp+CCh] [rbp-3Ch]
  __int128 v61; // [rsp+DCh] [rbp-2Ch]
  __int128 v62; // [rsp+ECh] [rbp-1Ch]
  __int128 v63; // [rsp+FCh] [rbp-Ch]
  __int128 v64; // [rsp+10Ch] [rbp+4h]
  __int128 v65; // [rsp+11Ch] [rbp+14h]
  __int128 v66; // [rsp+12Ch] [rbp+24h]
  __int16 v67; // [rsp+13Ch] [rbp+34h]
  wchar_t pszDest[69]; // [rsp+13Eh] [rbp+36h] BYREF
  size_t pcchToRead; // [rsp+1C8h] [rbp+C0h] BYREF
  STRSAFE_PCNZWCH ppszSrc; // [rsp+1D0h] [rbp+C8h] BYREF
  _UNICODE_STRING DestinationString; // [rsp+1D8h] [rbp+D0h] BYREF
  GUID rguid; // [rsp+1E8h] [rbp+E0h] BYREF
  _IO_STATUS_BLOCK IoStatusBlock; // [rsp+1F8h] [rbp+F0h] BYREF
  unsigned __int16 v74[64]; // [rsp+208h] [rbp+100h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2D0h] [rbp+1C8h]

  if ( !a4 || !a1 || !*(_DWORD *)a1 || *((_DWORD *)a1 + 1) < 0xC0u || (*((_WORD *)a1 + 33) & 0xFEE) != 0 )
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0xC1,
             (unsigned int)"onecore\\vm\\dv\\vmbus\\pipes\\dll\\server.cpp",
             (const char *)0x57,
             cchToCopy);
  memset_0(&InBuffer, 0, 0x128u);
  ppszSrc = (STRSAFE_PCNZWCH)*((_QWORD *)a1 + 23);
  pcchToRead = 64;
  v9 = StringExValidateSrcW(&ppszSrc, &pcchToRead, v8, 0x100u);
  if ( v9 < 0 )
    return wil::details::in1diag3::Return_Win32Msg(
             retaddr,
             (void *)0xCE,
             (unsigned int)"onecore\\vm\\dv\\vmbus\\pipes\\dll\\server.cpp",
             (const char *)0x57,
             (unsigned int)"%ls",
             *((const char **)a1 + 23));
  pcchNewDestLength = 0;
  v11 = StringCopyWorkerW_0(pszDest, v10, &pcchNewDestLength, ppszSrc, pcchToRead);
  if ( v11 < 0 )
    return wil::details::in1diag3::Return_Win32Msg(
             retaddr,
             (void *)0xCE,
             (unsigned int)"onecore\\vm\\dv\\vmbus\\pipes\\dll\\server.cpp",
             (const char *)0x57,
             (unsigned int)"%ls",
             *((const char **)a1 + 23));
  v14 = *(_OWORD *)((char *)a1 + 28);
  v15 = *((_WORD *)a1 + 33);
  v16 = *(_OWORD *)((char *)a1 + 44);
  v67 = pcchNewDestLength;
  v17 = v52;
  if ( (v15 & 1) != 0 )
    v17 = 1;
  v52 = v17;
  v55 = v14;
  v56 = v16;
  rguid = 0;
  if ( (v15 & 0x100) == 0 )
  {
    v12 = *((_QWORD *)a1 + 1);
    if ( (v15 & 0x2000) != 0 )
    {
      if ( v12 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
      {
        InBuffer = *((_QWORD *)a1 + 1);
        goto LABEL_12;
      }
      v33 = retaddr;
      v34 = 87;
      v35 = 227;
    }
    else
    {
      if ( !v12 )
        v12 = *((_QWORD *)a1 + 2) - _mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
      if ( v12 )
      {
        rguid = *(GUID *)((char *)a1 + 8);
        goto LABEL_12;
      }
      v33 = retaddr;
      v34 = 87;
      v35 = 236;
    }
    return wil::details::in1diag3::Return_Win32(
             v33,
             (void *)v35,
             (unsigned int)"onecore\\vm\\dv\\vmbus\\pipes\\dll\\server.cpp",
             (const char *)v34,
             cchToCopya);
  }
LABEL_12:
  if ( (v15 & 0x10) != 0 || a3 != 8 )
  {
    v53 = 1;
    if ( (v15 & 0x4000) != 0 )
    {
      v33 = retaddr;
      v34 = 50;
      v35 = 250;
      return wil::details::in1diag3::Return_Win32(
               v33,
               (void *)v35,
               (unsigned int)"onecore\\vm\\dv\\vmbus\\pipes\\dll\\server.cpp",
               (const char *)v34,
               cchToCopya);
    }
  }
  v18 = *(_OWORD *)((char *)a1 + 68);
  v19 = v54;
  v20 = *(_OWORD *)((char *)a1 + 84);
  if ( (v15 & 0x1000) != 0 )
    v19 = 1;
  v57 = a3;
  v54 = v19;
  v58 = *((_WORD *)a1 + 32);
  v60 = v18;
  v21 = *(_OWORD *)((char *)a1 + 100);
  v61 = v20;
  v22 = *(_OWORD *)((char *)a1 + 116);
  v62 = v21;
  v23 = *(_OWORD *)((char *)a1 + 132);
  v63 = v22;
  v24 = *(_OWORD *)((char *)a1 + 148);
  v64 = v23;
  v25 = *(_OWORD *)((char *)a1 + 164);
  v65 = v24;
  v66 = v25;
  if ( v15 < 0 )
    v59 |= 1u;
  v26 = 0;
  memset(ObjectAttributes, 0, 56);
  DestinationString = 0;
  if ( InBuffer )
  {
    v27 = L"\\??\\VMBusPipe\\pipe";
  }
  else
  {
    pcchNewDestLength = 0;
    lpsz = 0;
    v36 = StringCbCopyExW(v74, v12, (const unsigned __int16 *)1, &lpsz, &pcchNewDestLength, OpenOptions);
    if ( v36 < 0 )
      wil::details::in1diag3::_FailFast_Hr(retaddr, v37, v38, (const char *)(unsigned int)v36, cchToCopyd);
    if ( !StringFromGUID2(&rguid, lpsz, pcchNewDestLength) )
      wil::details::in1diag3::_FailFast_Unexpected(retaddr, v39, v40, v41);
    v27 = v74;
  }
  RtlInitUnicodeString(&DestinationString, v27);
  LODWORD(ObjectAttributes[1]) = 48;
  ObjectAttributes[2] = 0;
  LODWORD(ObjectAttributes[4]) = 64;
  ObjectAttributes[3] = &DestinationString;
  pcchToRead = 0;
  *(_OWORD *)&ObjectAttributes[5] = 0;
  IoStatusBlock = 0;
  v28 = NtOpenFile(
          (PHANDLE)&pcchToRead,
          0x1F01FFu,
          (POBJECT_ATTRIBUTES)&ObjectAttributes[1],
          &IoStatusBlock,
          3u,
          ~(a2 >> 25) & 0x20 | 0x40);
  if ( v28 >= 0 )
  {
    LODWORD(ppszSrc) = 0;
    if ( DeviceIoControl((HANDLE)pcchToRead, 0x22C018u, &InBuffer, 0x128u, 0, 0, (LPDWORD)&ppszSrc, 0) )
    {
      v26 = (void *)pcchToRead;
      goto LABEL_24;
    }
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x74,
                  (unsigned int)"onecore\\vm\\dv\\vmbus\\pipes\\dll\\server.cpp",
                  v32);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&pcchToRead);
  }
  else
  {
    LastError = wil::details::in1diag3::Return_NtStatus(retaddr, v29, v30, (const char *)(unsigned int)v28, cchToCopyb);
    if ( pcchToRead - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle((HANDLE)pcchToRead);
  }
  if ( LastError >= 0 )
  {
LABEL_24:
    *a4 = v26;
    return 0;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x10F,
    (unsigned int)"onecore\\vm\\dv\\vmbus\\pipes\\dll\\server.cpp",
    (const char *)(unsigned int)LastError,
    cchToCopyc);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(ObjectAttributes);
  return LastError;
}

```

## disassembly

```asm
0x1800012b0  mov     r11, rsp
0x1800012b3  push    rbp
0x1800012b4  push    rbx
0x1800012b5  push    rsi
0x1800012b6  push    rdi
0x1800012b7  push    r14
0x1800012b9  lea     rbp, [r11-1C8h]
0x1800012c0  sub     rsp, 2A0h
0x1800012c7  mov     rax, cs:__security_cookie
0x1800012ce  xor     rax, rsp
0x1800012d1  mov     [rbp+1C0h+var_40], rax
0x1800012d8  mov     rsi, r9
0x1800012db  mov     r14d, r8d
0x1800012de  mov     edi, edx
0x1800012e0  mov     rbx, rcx
0x1800012e3  test    r9, r9
0x1800012e6  jz      loc_1800017A9
0x1800012ec  test    rcx, rcx
0x1800012ef  jz      loc_1800017A9
0x1800012f5  cmp     dword ptr [rcx], 1
0x1800012f8  jb      loc_1800017A9
0x1800012fe  cmp     dword ptr [rcx+4], 0C0h
0x180001305  jb      loc_1800017A9
0x18000130b  movzx   eax, word ptr [rcx+42h]
0x18000130f  test    eax, 0FFFF0FEEh
0x180001314  jnz     loc_1800017A9
0x18000131a  mov     [r11-30h], r12
0x18000131e  lea     rcx, [rbp+1C0h+InBuffer]; void *
0x180001322  xor     edx, edx; Val
0x180001324  mov     [r11-38h], r15
0x180001328  mov     r8d, 128h; Size
0x18000132e  call    memset_0
0x180001333  mov     rax, [rbx+0B8h]
0x18000133a  lea     rdx, [rbp+1C0h+pcchToRead]; pcchToRead
0x180001341  mov     r12d, 100h
0x180001347  mov     [rbp+1C0h+ppszSrc], rax
0x18000134e  mov     r9d, r12d; dwFlags
0x180001351  mov     [rbp+1C0h+pcchToRead], 40h ; '@'
0x18000135c  lea     rcx, [rbp+1C0h+ppszSrc]; ppszSrc
0x180001363  mov     r10d, 40h ; '@'
0x180001369  call    StringExValidateSrcW
0x18000136e  xor     r15d, r15d
0x180001371  test    eax, eax
0x180001373  js      short loc_1800013AD
0x180001375  mov     rax, [rbp+1C0h+pcchToRead]
0x18000137c  lea     r8, [rsp+2C0h+pcchNewDestLength]; pcchNewDestLength
0x180001381  mov     r9, [rbp+1C0h+ppszSrc]; pszSrc
0x180001388  lea     rcx, [rbp+1C0h+pszDest]; pszDest
0x18000138c  mov     edx, r10d; cchDest
0x18000138f  mov     [rsp+2C0h+cchToCopy], rax; unsigned int
0x180001394  mov     [rsp+2C0h+pcchNewDestLength], r15
0x180001399  call    StringCopyWorkerW_0
0x18000139e  mov     r10d, 40h ; '@'
0x1800013a4  sub     r10, [rsp+2C0h+pcchNewDestLength]
0x1800013a9  test    eax, eax
0x1800013ab  jns     short loc_1800013F3
0x1800013ad  cmp     eax, 8007007Ah
0x1800013b2  jz      short loc_1800013EF
0x1800013b4  mov     rax, [rbx+0B8h]
0x1800013bb  lea     r8, aOnecoreVmDvVmb_0; "onecore\\vm\\dv\\vmbus\\pipes\\dll\\ser"...
0x1800013c2  mov     rcx, [rbp+1C8h]; this
0x1800013c9  mov     r9d, 57h ; 'W'; char *
0x1800013cf  mov     qword ptr [rsp+2C0h+OpenOptions], rax; char *
0x1800013d4  mov     edx, 0CEh; void *
0x1800013d9  lea     rax, aLs; "%ls"
0x1800013e0  mov     [rsp+2C0h+cchToCopy], rax; unsigned int
0x1800013e5  call    ?Return_Win32Msg@in1diag3@details@wil@@YAJPEAXIPEBDK1ZZ; wil::details::in1diag3::Return_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x1800013ea  jmp     loc_18000159B
0x1800013ef  test    eax, eax
0x1800013f1  js      short loc_1800013B4
0x1800013f3  movups  xmm0, xmmword ptr [rbx+1Ch]
0x1800013f7  movzx   ecx, word ptr [rbx+42h]
0x1800013fb  mov     eax, 40h ; '@'
0x180001400  movups  xmm1, xmmword ptr [rbx+2Ch]
0x180001404  sub     ax, r10w
0x180001408  mov     r8d, 1; unsigned __int16 *
0x18000140e  mov     [rbp+1C0h+var_18C], ax
0x180001412  test    cl, 1
0x180001415  movzx   eax, [rbp+1C0h+var_228]
0x180001419  cmovnz  eax, r8d
0x18000141d  mov     [rbp+1C0h+var_228], al
0x180001420  movups  [rbp+1C0h+var_224], xmm0
0x180001424  xorps   xmm0, xmm0
0x180001427  movups  [rbp+1C0h+var_214], xmm1
0x18000142b  movups  xmmword ptr [rbp+1C0h+rguid.Data1], xmm0
0x180001432  test    r12w, cx
0x180001436  jz      loc_18000161A
0x18000143c  test    cl, 10h
0x18000143f  jnz     loc_1800016A6
0x180001445  cmp     r14d, 8
0x180001449  jnz     loc_1800016A6
0x18000144f  movups  xmm0, xmmword ptr [rbx+44h]
0x180001453  movzx   eax, [rbp+1C0h+var_226]
0x180001457  bt      cx, 0Ch
0x18000145c  movups  xmm1, xmmword ptr [rbx+54h]
0x180001460  cmovb   eax, r8d
0x180001464  mov     [rbp+1C0h+var_204], r14d
0x180001468  mov     [rbp+1C0h+var_226], al
0x18000146b  movzx   eax, word ptr [rbx+40h]
0x18000146f  mov     [rbp+1C0h+var_200], ax
0x180001473  movups  [rbp+1C0h+var_1FC], xmm0
0x180001477  movups  xmm0, xmmword ptr [rbx+64h]
0x18000147b  movups  [rbp+1C0h+var_1EC], xmm1
0x18000147f  movups  xmm1, xmmword ptr [rbx+74h]
0x180001483  movups  [rbp+1C0h+var_1DC], xmm0
0x180001487  movups  xmm0, xmmword ptr [rbx+84h]
0x18000148e  movups  [rbp+1C0h+var_1CC], xmm1
0x180001492  movups  xmm1, xmmword ptr [rbx+94h]
0x180001499  movups  [rbp+1C0h+var_1BC], xmm0
0x18000149d  movups  xmm0, xmmword ptr [rbx+0A4h]
0x1800014a4  movups  [rbp+1C0h+var_1AC], xmm1
0x1800014a8  movups  [rbp+1C0h+var_19C], xmm0
0x1800014ac  test    cx, cx
0x1800014af  js      loc_1800016D0
0x1800014b5  xorps   xmm1, xmm1
0x1800014b8  mov     rbx, r15
0x1800014bb  xorps   xmm0, xmm0
0x1800014be  mov     qword ptr [rsp+2C0h+ObjectAttributes], rbx
0x1800014c3  movups  xmmword ptr [rbp+1C0h+DestinationString.Length], xmm0
0x1800014ca  movups  xmmword ptr [rsp+2C0h+ObjectAttributes+8], xmm1
0x1800014cf  movups  xmmword ptr [rsp+2C0h+ObjectAttributes+18h], xmm1
0x1800014d4  movups  xmmword ptr [rsp+2C0h+ObjectAttributes+28h], xmm1
0x1800014d9  cmp     [rbp+1C0h+InBuffer], rbx
0x1800014dd  jz      loc_1800016DA
0x1800014e3  lea     rdx, SourceString; "\\??\\VMBusPipe\\pipe"
0x1800014ea  lea     rcx, [rbp+1C0h+DestinationString]; DestinationString
0x1800014f1  call    cs:__imp_RtlInitUnicodeString
0x1800014f7  shr     edi, 19h
0x1800014fa  lea     rax, [rbp+1C0h+DestinationString]
0x180001501  xorps   xmm0, xmm0
0x180001504  mov     dword ptr [rsp+2C0h+ObjectAttributes+8], 30h ; '0'
0x18000150c  not     edi
0x18000150e  mov     qword ptr [rsp+2C0h+ObjectAttributes+10h], r15
0x180001513  and     edi, 20h
0x180001516  mov     dword ptr [rsp+2C0h+ObjectAttributes+20h], 40h ; '@'
0x18000151e  or      edi, 40h
0x180001521  mov     qword ptr [rsp+2C0h+ObjectAttributes+18h], rax
0x180001526  mov     [rsp+2C0h+OpenOptions], edi; OpenOptions
0x18000152a  lea     r9, [rbp+1C0h+IoStatusBlock]; IoStatusBlock
0x180001531  lea     r8, [rsp+2C0h+ObjectAttributes+8]; ObjectAttributes
0x180001536  mov     dword ptr [rsp+2C0h+cchToCopy], 3; int
0x18000153e  mov     edx, 1F01FFh; DesiredAccess
0x180001543  mov     [rbp+1C0h+pcchToRead], r15
0x18000154a  lea     rcx, [rbp+1C0h+pcchToRead]; FileHandle
0x180001551  movdqu  xmmword ptr [rsp+2C0h+ObjectAttributes+28h], xmm0
0x180001557  movups  xmmword ptr [rbp+1C0h+IoStatusBlock], xmm0
0x18000155e  call    cs:__imp_NtOpenFile
0x180001564  test    eax, eax
0x180001566  jns     short loc_1800015C8
0x180001568  mov     rcx, [rbp+1C8h]; this
0x18000156f  mov     r9d, eax; char *
0x180001572  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180001577  mov     rcx, [rbp+1C0h+pcchToRead]; hObject
0x18000157e  mov     edi, eax
0x180001580  lea     rax, [rcx-1]
0x180001584  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180001588  jbe     loc_180001747
0x18000158e  test    edi, edi
0x180001590  js      loc_18000177D
0x180001596  mov     [rsi], rbx
0x180001599  xor     eax, eax
0x18000159b  mov     r12, [rsp+298h]
0x1800015a3  mov     r15, [rsp+2C0h+var_30]
0x1800015ab  mov     rcx, [rbp+1C0h+var_40]
0x1800015b2  xor     rcx, rsp; StackCookie
0x1800015b5  call    __security_check_cookie
0x1800015ba  add     rsp, 2A0h
0x1800015c1  pop     r14
0x1800015c3  pop     rdi
0x1800015c4  pop     rsi
0x1800015c5  pop     rbx
0x1800015c6  pop     rbp
0x1800015c7  retn
0x1800015c8  mov     rcx, [rbp+1C0h+pcchToRead]; hDevice
0x1800015cf  lea     rax, [rbp+1C0h+ppszSrc]
0x1800015d6  mov     [rsp+2C0h+lpOverlapped], r15; lpOverlapped
0x1800015db  lea     r8, [rbp+1C0h+InBuffer]; lpInBuffer
0x1800015df  mov     [rsp+2C0h+lpBytesReturned], rax; lpBytesReturned
0x1800015e4  mov     r9d, 128h; nInBufferSize
0x1800015ea  mov     [rsp+2C0h+OpenOptions], r15d; nOutBufferSize
0x1800015ef  mov     edx, 22C018h; dwIoControlCode
0x1800015f4  mov     [rsp+2C0h+cchToCopy], r15; lpOutBuffer
0x1800015f9  mov     dword ptr [rbp+1C0h+ppszSrc], r15d
0x180001600  call    cs:__imp_DeviceIoControl
0x180001606  test    eax, eax
0x180001608  jz      loc_180001752
0x18000160e  mov     rbx, [rbp+1C0h+pcchToRead]
0x180001615  jmp     loc_180001596
0x18000161a  bt      cx, 0Dh
0x18000161f  mov     rdx, [rbx+8]
0x180001623  jnb     short loc_18000165B
0x180001625  lea     rax, [rdx-1]
0x180001629  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000162d  ja      short loc_180001638
0x18000162f  mov     [rbp+1C0h+InBuffer], rdx
0x180001633  jmp     loc_18000143C
0x180001638  mov     rcx, [rbp+1C8h]; this
0x18000163f  lea     r8, aOnecoreVmDvVmb_0; "onecore\\vm\\dv\\vmbus\\pipes\\dll\\ser"...
0x180001646  mov     r9d, 57h ; 'W'; char *
0x18000164c  mov     edx, 0E3h; void *
0x180001651  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180001656  jmp     loc_18000159B
0x18000165b  movq    rax, xmm0
0x180001660  sub     rdx, rax
0x180001663  jnz     short loc_180001676
0x180001665  mov     rdx, [rbx+10h]
0x180001669  psrldq  xmm0, 8
0x18000166e  movq    rax, xmm0
0x180001673  sub     rdx, rax
0x180001676  test    rdx, rdx
0x180001679  jnz     short loc_180001696
0x18000167b  mov     rcx, [rbp+1C8h]
0x180001682  lea     r8, aOnecoreVmDvVmb_0; "onecore\\vm\\dv\\vmbus\\pipes\\dll\\ser"...
0x180001689  mov     r9d, 57h ; 'W'
0x18000168f  mov     edx, 0ECh
0x180001694  jmp     short loc_180001651
0x180001696  movups  xmm0, xmmword ptr [rbx+8]
0x18000169a  movups  xmmword ptr [rbp+1C0h+rguid.Data1], xmm0
0x1800016a1  jmp     loc_18000143C
0x1800016a6  bt      cx, 0Eh
0x1800016ab  mov     [rbp+1C0h+var_227], r8b
0x1800016af  jnb     loc_18000144F
0x1800016b5  mov     rcx, [rbp+1C8h]
0x1800016bc  lea     r8, aOnecoreVmDvVmb_0; "onecore\\vm\\dv\\vmbus\\pipes\\dll\\ser"...
0x1800016c3  mov     r9d, 32h ; '2'
0x1800016c9  mov     edx, 0FAh
0x1800016ce  jmp     short loc_180001651
0x1800016d0  or      [rbp+1C0h+var_1FE], r8w
0x1800016d5  jmp     loc_1800014B5
0x1800016da  lea     rax, [rsp+2C0h+pcchNewDestLength]
0x1800016df  mov     [rsp+2C0h+pcchNewDestLength], r15
0x1800016e4  lea     r9, [rsp+2C0h+lpsz]; unsigned __int16 **
0x1800016e9  mov     [rsp+2C0h+cchToCopy], rax; int
0x1800016ee  lea     rcx, [rbp+1C0h+var_C0]; unsigned __int16 *
0x1800016f5  mov     [rsp+2C0h+lpsz], r15
0x1800016fa  call    ?StringCbCopyExW@@YAJPEAG_KPEBGPEAPEAGPEA_KK@Z; StringCbCopyExW(ushort *,unsigned __int64,ushort const *,ushort * *,unsigned __int64 *,ulong)
0x1800016ff  test    eax, eax
0x180001701  jns     short loc_180001713
0x180001703  mov     rcx, [rbp+1C8h]; this
0x18000170a  mov     r9d, eax; char *
0x18000170d  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x180001713  mov     r8d, dword ptr [rsp+2C0h+pcchNewDestLength]; cchMax
0x180001718  lea     rcx, [rbp+1C0h+rguid]; rguid
0x18000171f  mov     rdx, [rsp+2C0h+lpsz]; lpsz
0x180001724  call    cs:__imp_StringFromGUID2
0x18000172a  test    eax, eax
0x18000172c  jnz     short loc_18000173B
0x18000172e  mov     rcx, [rbp+1C8h]; this
0x180001735  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18000173b  lea     rdx, [rbp+1C0h+var_C0]
0x180001742  jmp     loc_1800014EA
0x180001747  call    cs:__imp_CloseHandle
0x18000174d  jmp     loc_18000158E
0x180001752  mov     rcx, [rbp+1C8h]; this
0x180001759  lea     r8, aOnecoreVmDvVmb_0; "onecore\\vm\\dv\\vmbus\\pipes\\dll\\ser"...
0x180001760  mov     edx, 74h ; 't'; void *
0x180001765  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000176a  lea     rcx, [rbp+1C0h+pcchToRead]
0x180001771  mov     edi, eax
0x180001773  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180001778  jmp     loc_18000158E
0x18000177d  mov     rcx, [rbp+1C8h]; this
0x180001784  lea     r8, aOnecoreVmDvVmb_0; "onecore\\vm\\dv\\vmbus\\pipes\\dll\\ser"...
0x18000178b  mov     r9d, edi; char *
0x18000178e  mov     edx, 10Fh; void *
0x180001793  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180001798  lea     rcx, [rsp+2C0h+ObjectAttributes]
0x18000179d  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800017a2  mov     eax, edi
0x1800017a4  jmp     loc_18000159B
0x1800017a9  mov     rcx, [rbp+1C8h]; this
0x1800017b0  lea     r8, aOnecoreVmDvVmb_0; "onecore\\vm\\dv\\vmbus\\pipes\\dll\\ser"...
0x1800017b7  mov     r9d, 57h ; 'W'; char *
0x1800017bd  mov     edx, 0C1h; void *
0x1800017c2  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800017c7  jmp     loc_1800015AB
```
