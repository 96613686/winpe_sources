# CTpLogger::LogExchange(wchar_t const *,wchar_t const *,wchar_t const *,ulong,ulong,long,ulong,void *,ulong,IWerByteStream *,ulong,long,ulong,ulong,long,ulong,void *,ulong,ulong,wchar_t const *)

- ea: `0x1800a497c`
- end: `0x1800a4f42`
- name: `?LogExchange@CTpLogger@@QEAAJPEB_W00KKJKPEAXKPEAUIWerByteStream@@KJKKJK1KK0@Z`
- size: `1478`
- prototype: `__int64 __fastcall(CTpLogger *__hidden this, const wchar_t *, const wchar_t *, const wchar_t *, unsigned int, unsigned int, int, unsigned int, void *, unsigned int, struct IWerByteStream *, unsigned int, int, unsigned int, unsigned int, int, unsigned int, void *, unsigned int, unsigned int, const wchar_t *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003e2b4`

## callees

- `0x180018090`
- `0x180053300`
- `0x180053d3c`
- `0x180053d48`
- `0x1800a497c`
- `0x1800af010`
- `0x1800b2010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_fread` at `0x1800a4d2f`
- `api-ms-win-crt-private-l1-1-0!_o_fread` at `0x1800a4d2f`
- `api-ms-win-crt-private-l1-1-0!_o_fseek` at `0x1800a4d0d`
- `api-ms-win-crt-private-l1-1-0!_o_fseek` at `0x1800a4edb`
- `api-ms-win-crt-private-l1-1-0!_o_fseek` at `0x1800a4d0d`
- `api-ms-win-crt-private-l1-1-0!_o_fseek` at `0x1800a4edb`
- `api-ms-win-crt-private-l1-1-0!_o_fwrite` at `0x1800a4a6e`
- `api-ms-win-crt-private-l1-1-0!_o_fwrite` at `0x1800a4b1f`
- `api-ms-win-crt-private-l1-1-0!_o_fwrite` at `0x1800a4b95`
- `api-ms-win-crt-private-l1-1-0!_o_fwrite` at `0x1800a4efd`
- `api-ms-win-crt-private-l1-1-0!_o_fwrite` at `0x1800a4a6e`
- `api-ms-win-crt-private-l1-1-0!_o_fwrite` at `0x1800a4b1f`
- `api-ms-win-crt-private-l1-1-0!_o_fwrite` at `0x1800a4b95`
- `api-ms-win-crt-private-l1-1-0!_o_fwrite` at `0x1800a4efd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800a4a1c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800a4a1c`

## string_xrefs

- `0x1800a4cc6`: `	session-name: %ls\n	server-name: %ls\n	request-url: %ls\n	exchange-name: %ls\n	connect-time: %u\n	proxy-resolution-time: %u\n	xml-write-rc: %08X\n	xml-write-time: %u\n	send-xml-size: %u\n	send-xml-log-offset: %08X\n	send-bin-size: %u\n	send-bin-log-offset: %08X\n	send-time: %u\n	xml-parse-rc: %08X\n	xml-parse-time: %u\n	msft-root-check-time: %u\n	net-result-rc: %08X\n	receive-http-code: %u\n	receive-size: %u\n	receive-time: %u\n	receive-log-offset: %08X\n	headers: %ls\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CTpLogger::LogExchange(
        CTpLogger *this,
        const wchar_t *a2,
        const wchar_t *a3,
        const wchar_t *a4,
        unsigned int a5,
        unsigned int a6,
        int a7,
        unsigned int a8,
        void *a9,
        unsigned int a10,
        struct IWerByteStream *a11,
        unsigned int a12,
        int a13,
        unsigned int a14,
        unsigned int a15,
        int a16,
        unsigned int a17,
        void *a18,
        unsigned int a19,
        unsigned int a20,
        const wchar_t *a21)
{
  unsigned int v23; // edx
  int *v24; // rsi
  unsigned int v25; // ebx
  int v26; // r13d
  unsigned int v27; // eax
  int v28; // r13d
  FILE *v29; // rcx
  const wchar_t *v30; // r8
  const wchar_t *v31; // rax
  const wchar_t *v32; // rcx
  int v33; // r13d
  FILE *v34; // rcx
  int v35; // eax
  int v36; // eax
  unsigned int v37; // r9d
  int v38; // [rsp+B0h] [rbp-90h]
  unsigned int v39; // [rsp+C0h] [rbp-80h] BYREF
  int v40; // [rsp+C4h] [rbp-7Ch]
  unsigned int v41; // [rsp+C8h] [rbp-78h]
  int v42; // [rsp+CCh] [rbp-74h]
  int v43; // [rsp+D0h] [rbp-70h]
  int v44; // [rsp+D4h] [rbp-6Ch]
  __int64 v45; // [rsp+D8h] [rbp-68h] BYREF
  void *v46; // [rsp+E0h] [rbp-60h]
  const wchar_t *v47; // [rsp+E8h] [rbp-58h]
  const wchar_t *v48; // [rsp+F0h] [rbp-50h]
  const wchar_t *v49; // [rsp+F8h] [rbp-48h]
  const wchar_t *v50; // [rsp+100h] [rbp-40h]
  char *v51; // [rsp+108h] [rbp-38h] BYREF
  char v52; // [rsp+110h] [rbp-30h]
  _OWORD v53[5]; // [rsp+120h] [rbp-20h] BYREF
  __int128 Buffer; // [rsp+170h] [rbp+30h] BYREF
  __int128 v55; // [rsp+180h] [rbp+40h]
  __int128 v56; // [rsp+190h] [rbp+50h]
  __int128 v57; // [rsp+1A0h] [rbp+60h]
  __int128 v58; // [rsp+1B0h] [rbp+70h]
  _BYTE v59[4096]; // [rsp+1C0h] [rbp+80h] BYREF

  v48 = a4;
  v49 = a3;
  v50 = a2;
  v47 = a21;
  v46 = a18;
  memset_0(&Buffer, 0, 0x50u);
  if ( !*((_DWORD *)this + 31) )
    return 1;
  v44 = -1;
  v43 = -1;
  v40 = 0;
  v42 = -1;
  v51 = (char *)this + 8;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  v52 = 1;
  v23 = *((_DWORD *)this + 28);
  v41 = v23;
  *((_DWORD *)this + 28) = v23 + 1;
  if ( !*((_QWORD *)this + 13) )
    goto LABEL_21;
  v24 = (int *)((char *)this + 116);
  if ( !a10 )
  {
LABEL_8:
    if ( *((_DWORD *)this + 32) )
    {
      if ( a11 )
      {
        v39 = 0;
        v45 = 0;
        if ( (*(int (__fastcall **)(struct IWerByteStream *, _QWORD, _QWORD, __int64 *))(*(_QWORD *)a11 + 16LL))(
               a11,
               0,
               0,
               &v45) >= 0 )
        {
          v24 = (int *)((char *)this + 116);
          v43 = *((_DWORD *)this + 29);
          v26 = 0;
          v40 = 0;
          if ( (**(int (__fastcall ***)(struct IWerByteStream *, _BYTE *, __int64, unsigned int *, _QWORD))a11)(
                 a11,
                 v59,
                 4096,
                 &v39,
                 0) >= 0 )
          {
            do
            {
              if ( !v39 )
                break;
              if ( (unsigned int)_o_fwrite(v59, v39, 1) != 1 )
                break;
              v27 = v39;
              *v24 += v39;
              v26 += v27;
            }
            while ( (**(int (__fastcall ***)(struct IWerByteStream *, _BYTE *, __int64, unsigned int *, _QWORD))a11)(
                      a11,
                      v59,
                      4096,
                      &v39,
                      0) >= 0 );
            v40 = v26;
          }
          (*(void (__fastcall **)(struct IWerByteStream *, _QWORD, _QWORD, _QWORD))(*(_QWORD *)a11 + 16LL))(
            a11,
            (unsigned int)v45,
            0,
            0);
        }
      }
    }
    if ( a19 )
    {
      v28 = *v24;
      if ( (unsigned int)_o_fwrite(v46, a19, 1) != 1 )
        goto LABEL_6;
      *v24 += a19;
      v23 = v41;
LABEL_22:
      v29 = (FILE *)*((_QWORD *)this + 12);
      if ( v29 )
      {
        if ( fwprintf(v29, L"exchange %u {\n", v23) < 0 )
          goto LABEL_6;
        v30 = L"none";
        v31 = v47;
        if ( !v47 )
          v31 = L"none";
        v32 = v48;
        if ( !v48 )
          v32 = L"none";
        if ( *((_QWORD *)this + 10) )
          v30 = (const wchar_t *)*((_QWORD *)this + 10);
        v38 = v28;
        v33 = v40;
        if ( fwprintf(
               *((FILE *const *)this + 12),
               L"\tsession-name: %ls\n"
                "\tserver-name: %ls\n"
                "\trequest-url: %ls\n"
                "\texchange-name: %ls\n"
                "\tconnect-time: %u\n"
                "\tproxy-resolution-time: %u\n"
                "\txml-write-rc: %08X\n"
                "\txml-write-time: %u\n"
                "\tsend-xml-size: %u\n"
                "\tsend-xml-log-offset: %08X\n"
                "\tsend-bin-size: %u\n"
                "\tsend-bin-log-offset: %08X\n"
                "\tsend-time: %u\n"
                "\txml-parse-rc: %08X\n"
                "\txml-parse-time: %u\n"
                "\tmsft-root-check-time: %u\n"
                "\tnet-result-rc: %08X\n"
                "\treceive-http-code: %u\n"
                "\treceive-size: %u\n"
                "\treceive-time: %u\n"
                "\treceive-log-offset: %08X\n"
                "\theaders: %ls\n",
               v30,
               v50,
               v49,
               v32,
               a5,
               a6,
               a7,
               a8,
               a10,
               v44,
               v40,
               v43,
               a12,
               a13,
               a14,
               a15,
               a16,
               a17,
               a19,
               a20,
               v38,
               v31) < 0
          || fwprintf(*((FILE *const *)this + 12), L"}\n") < 0 )
        {
          goto LABEL_6;
        }
      }
      else
      {
        v33 = v40;
      }
      v34 = (FILE *)*((_QWORD *)this + 11);
      if ( v34 )
      {
        if ( fseek(v34, 0, 0) )
          goto LABEL_6;
        v35 = fread(&Buffer, 0x50u, 1u, *((FILE **)this + 11));
        if ( v35 )
        {
          if ( v35 != 1 )
            goto LABEL_6;
          v36 = Buffer;
        }
        else
        {
          memset_0(v53, 0, sizeof(v53));
          Buffer = v53[0];
          v55 = v53[1];
          v56 = v53[2];
          v57 = v53[3];
          v58 = v53[4];
          v36 = 3;
          LODWORD(Buffer) = 3;
        }
        if ( v36 == 3 )
        {
          DWORD1(Buffer) = (a5 + DWORD1(Buffer) * HIDWORD(Buffer)) / (HIDWORD(Buffer) + 1);
          DWORD2(Buffer) = (a6 + DWORD2(Buffer) * HIDWORD(Buffer)) / (HIDWORD(Buffer) + 1);
          ++HIDWORD(Buffer);
          if ( a10 )
          {
            v37 = v56 + 1;
            LODWORD(v55) = (a10 + (_DWORD)v55 * (_DWORD)v56) / ((int)v56 + 1);
            if ( a11 )
            {
              DWORD1(v55) = (v33 + DWORD1(v55) * DWORD1(v56)) / (unsigned int)(DWORD1(v56) + 1);
              ++DWORD1(v56);
            }
            DWORD2(v55) = (a12 + (_DWORD)v56 * DWORD2(v55)) / v37;
            HIDWORD(v55) = (a8 + (_DWORD)v56 * HIDWORD(v55)) / v37;
            LODWORD(v56) = v56 + 1;
          }
          if ( a19 )
          {
            DWORD2(v56) = (a19 + DWORD2(v56) * DWORD1(v57)) / (DWORD1(v57) + 1);
            HIDWORD(v56) = (a20 + DWORD1(v57) * HIDWORD(v56)) / (DWORD1(v57) + 1);
            LODWORD(v57) = (a14 + DWORD1(v57) * (_DWORD)v57) / (DWORD1(v57) + 1);
            ++DWORD1(v57);
          }
          if ( a15 != -1 )
          {
            DWORD2(v58) = (a15 + DWORD2(v58) * HIDWORD(v58)) / (HIDWORD(v58) + 1);
            ++HIDWORD(v58);
          }
          if ( a7 < 0 )
            ++DWORD2(v57);
          if ( a13 < 0 )
            ++HIDWORD(v57);
          if ( a16 < 0 )
            LODWORD(v58) = v58 + 1;
          if ( a17 - 400 <= 0xC7 )
            ++DWORD1(v58);
        }
        if ( fseek(*((FILE **)this + 11), 0, 0) || (unsigned int)_o_fwrite(&Buffer, 80, 1) != 1 )
          goto LABEL_6;
      }
      v25 = 0;
      goto LABEL_60;
    }
    v23 = v41;
LABEL_21:
    v28 = v42;
    goto LABEL_22;
  }
  v44 = *v24;
  if ( (unsigned int)_o_fwrite(a9, a10, 1) == 1 )
  {
    *v24 += a10;
    goto LABEL_8;
  }
LABEL_6:
  v25 = -2147467259;
LABEL_60:
  utl::unique_lock<utl::recursive_mutex>::~unique_lock<utl::recursive_mutex>(&v51);
  return v25;
}

```

## disassembly

```asm
0x1800a497c  push    rbp
0x1800a497e  push    rbx
0x1800a497f  push    rsi
0x1800a4980  push    rdi
0x1800a4981  push    r12
0x1800a4983  push    r13
0x1800a4985  push    r14
0x1800a4987  push    r15
0x1800a4989  lea     rbp, [rsp-1098h]
0x1800a4991  mov     eax, 11D8h
0x1800a4996  call    _alloca_probe
0x1800a499b  sub     rsp, rax
0x1800a499e  mov     rax, cs:__security_cookie
0x1800a49a5  xor     rax, rsp
0x1800a49a8  mov     [rbp+10D0h+var_50], rax
0x1800a49af  mov     [rbp+10D0h+var_1120], r9
0x1800a49b3  mov     [rbp+10D0h+var_1118], r8
0x1800a49b7  mov     [rbp+10D0h+var_1110], rdx
0x1800a49bb  mov     rdi, rcx
0x1800a49be  mov     rax, [rbp+10D0h+arg_A0]
0x1800a49c5  mov     [rbp+10D0h+var_1128], rax
0x1800a49c9  mov     r13, [rbp+10D0h+arg_40]
0x1800a49d0  mov     r14, [rbp+10D0h+arg_50]
0x1800a49d7  mov     rax, [rbp+10D0h+arg_88]
0x1800a49de  mov     [rbp+10D0h+var_1130], rax
0x1800a49e2  xor     edx, edx; Val
0x1800a49e4  lea     r8d, [rdx+50h]; Size
0x1800a49e8  lea     rcx, [rbp+10D0h+Buffer]; void *
0x1800a49ec  call    memset_0
0x1800a49f1  cmp     dword ptr [rdi+7Ch], 0
0x1800a49f5  jnz     short loc_1800A4A01
0x1800a49f7  mov     eax, 1
0x1800a49fc  jmp     loc_1800A4F1E
0x1800a4a01  or      eax, 0FFFFFFFFh
0x1800a4a04  mov     [rbp+10D0h+var_113C], eax
0x1800a4a07  mov     [rbp+10D0h+var_1140], eax
0x1800a4a0a  mov     [rbp+10D0h+var_114C], 0
0x1800a4a11  mov     [rbp+10D0h+var_1144], eax
0x1800a4a14  lea     rcx, [rdi+8]; lpCriticalSection
0x1800a4a18  mov     [rbp+10D0h+var_1108], rcx
0x1800a4a1c  call    cs:__imp_EnterCriticalSection
0x1800a4a23  nop     dword ptr [rax+rax+00h]
0x1800a4a28  mov     ebx, 1
0x1800a4a2d  mov     [rbp+10D0h+var_1100], bl
0x1800a4a30  mov     edx, [rdi+70h]
0x1800a4a33  mov     [rbp+10D0h+var_1148], edx
0x1800a4a36  lea     eax, [rdx+1]
0x1800a4a39  mov     [rdi+70h], eax
0x1800a4a3c  mov     r9, [rdi+68h]
0x1800a4a40  mov     r15d, [rbp+10D0h+arg_90]
0x1800a4a47  mov     r12d, [rbp+10D0h+arg_48]
0x1800a4a4e  test    r9, r9
0x1800a4a51  jz      loc_1800A4BB4
0x1800a4a57  lea     rsi, [rdi+74h]
0x1800a4a5b  test    r12d, r12d
0x1800a4a5e  jz      short loc_1800A4A8B
0x1800a4a60  mov     eax, [rsi]
0x1800a4a62  mov     [rbp+10D0h+var_113C], eax
0x1800a4a65  mov     edx, r12d
0x1800a4a68  mov     r8d, ebx
0x1800a4a6b  mov     rcx, r13
0x1800a4a6e  call    cs:__imp__o_fwrite
0x1800a4a75  nop     dword ptr [rax+rax+00h]
0x1800a4a7a  cmp     eax, ebx
0x1800a4a7c  jz      short loc_1800A4A88
0x1800a4a7e  mov     ebx, 80004005h
0x1800a4a83  jmp     loc_1800A4F13
0x1800a4a88  add     [rsi], r12d
0x1800a4a8b  cmp     dword ptr [rdi+80h], 0
0x1800a4a92  jz      loc_1800A4B7F
0x1800a4a98  test    r14, r14
0x1800a4a9b  jz      loc_1800A4B7F
0x1800a4aa1  mov     [rbp+10D0h+var_1150], 0
0x1800a4aa8  mov     [rbp+10D0h+var_1138], 0
0x1800a4ab0  mov     rax, [r14]
0x1800a4ab3  lea     r9, [rbp+10D0h+var_1138]
0x1800a4ab7  xor     r8d, r8d
0x1800a4aba  xor     edx, edx
0x1800a4abc  mov     rcx, r14
0x1800a4abf  mov     rax, [rax+10h]
0x1800a4ac3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a4ac8  test    eax, eax
0x1800a4aca  js      loc_1800A4B7F
0x1800a4ad0  lea     rsi, [rdi+74h]
0x1800a4ad4  mov     eax, [rsi]
0x1800a4ad6  mov     [rbp+10D0h+var_1140], eax
0x1800a4ad9  xor     r13d, r13d
0x1800a4adc  mov     [rbp+10D0h+var_114C], r13d
0x1800a4ae0  mov     rax, [r14]
0x1800a4ae3  mov     [rsp+1210h+var_11F0], r13
0x1800a4ae8  lea     r9, [rbp+10D0h+var_1150]
0x1800a4aec  mov     r8d, 1000h
0x1800a4af2  lea     rdx, [rbp+10D0h+var_1050]
0x1800a4af9  mov     rcx, r14
0x1800a4afc  mov     rax, [rax]
0x1800a4aff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a4b04  test    eax, eax
0x1800a4b06  js      short loc_1800A4B67
0x1800a4b08  mov     eax, [rbp+10D0h+var_1150]
0x1800a4b0b  test    eax, eax
0x1800a4b0d  jz      short loc_1800A4B63
0x1800a4b0f  mov     edx, eax
0x1800a4b11  mov     r9, [rdi+68h]
0x1800a4b15  mov     r8, rbx
0x1800a4b18  lea     rcx, [rbp+10D0h+var_1050]
0x1800a4b1f  call    cs:__imp__o_fwrite
0x1800a4b26  nop     dword ptr [rax+rax+00h]
0x1800a4b2b  cmp     eax, ebx
0x1800a4b2d  jnz     short loc_1800A4B63
0x1800a4b2f  mov     eax, [rbp+10D0h+var_1150]
0x1800a4b32  add     [rsi], eax
0x1800a4b34  add     r13d, eax
0x1800a4b37  mov     rax, [r14]
0x1800a4b3a  mov     [rsp+1210h+var_11F0], 0
0x1800a4b43  lea     r9, [rbp+10D0h+var_1150]
0x1800a4b47  mov     r8d, 1000h
0x1800a4b4d  lea     rdx, [rbp+10D0h+var_1050]
0x1800a4b54  mov     rcx, r14
0x1800a4b57  mov     rax, [rax]
0x1800a4b5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a4b5f  test    eax, eax
0x1800a4b61  jns     short loc_1800A4B08
0x1800a4b63  mov     [rbp+10D0h+var_114C], r13d
0x1800a4b67  mov     rax, [r14]
0x1800a4b6a  mov     edx, dword ptr [rbp+10D0h+var_1138]
0x1800a4b6d  xor     r9d, r9d
0x1800a4b70  xor     r8d, r8d
0x1800a4b73  mov     rcx, r14
0x1800a4b76  mov     rax, [rax+10h]
0x1800a4b7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a4b7f  test    r15d, r15d
0x1800a4b82  jz      short loc_1800A4BB1
0x1800a4b84  mov     r13d, [rsi]
0x1800a4b87  mov     rdx, r15
0x1800a4b8a  mov     r9, [rdi+68h]
0x1800a4b8e  mov     r8, rbx
0x1800a4b91  mov     rcx, [rbp+10D0h+var_1130]
0x1800a4b95  call    cs:__imp__o_fwrite
0x1800a4b9c  nop     dword ptr [rax+rax+00h]
0x1800a4ba1  cmp     eax, ebx
0x1800a4ba3  jnz     loc_1800A4A7E
0x1800a4ba9  add     [rsi], r15d
0x1800a4bac  mov     edx, [rbp+10D0h+var_1148]
0x1800a4baf  jmp     short loc_1800A4BB8
0x1800a4bb1  mov     edx, [rbp+10D0h+var_1148]
0x1800a4bb4  mov     r13d, [rbp+10D0h+var_1144]
0x1800a4bb8  mov     rcx, [rdi+60h]; Stream
0x1800a4bbc  mov     esi, [rbp+10D0h+arg_70]
0x1800a4bc2  test    rcx, rcx
0x1800a4bc5  jz      loc_1800A4CF7
0x1800a4bcb  mov     r8d, edx
0x1800a4bce  lea     rdx, aExchangeU; "exchange %u {\n"
0x1800a4bd5  call    fwprintf
0x1800a4bda  test    eax, eax
0x1800a4bdc  js      loc_1800A4A7E
0x1800a4be2  lea     r8, aNone; "none"
0x1800a4be9  mov     rax, [rbp+10D0h+var_1128]
0x1800a4bed  test    rax, rax
0x1800a4bf0  cmovz   rax, r8
0x1800a4bf4  mov     rcx, [rbp+10D0h+var_1120]
0x1800a4bf8  test    rcx, rcx
0x1800a4bfb  cmovz   rcx, r8
0x1800a4bff  cmp     qword ptr [rdi+50h], 0
0x1800a4c04  cmovnz  r8, [rdi+50h]
0x1800a4c09  mov     [rsp+1210h+var_1158], rax
0x1800a4c11  mov     [rsp+1210h+var_1160], r13d
0x1800a4c19  mov     eax, [rbp+10D0h+arg_98]
0x1800a4c1f  mov     [rsp+1210h+var_1168], eax
0x1800a4c26  mov     [rsp+1210h+var_1170], r15d
0x1800a4c2e  mov     eax, [rbp+10D0h+arg_80]
0x1800a4c34  mov     [rsp+1210h+var_1178], eax
0x1800a4c3b  mov     eax, [rbp+10D0h+arg_78]
0x1800a4c41  mov     [rsp+1210h+var_1180], eax
0x1800a4c48  mov     [rsp+1210h+var_1188], esi
0x1800a4c4f  mov     eax, [rbp+10D0h+arg_68]
0x1800a4c55  mov     [rsp+1210h+var_1190], eax
0x1800a4c5c  mov     eax, [rbp+10D0h+arg_60]
0x1800a4c62  mov     [rsp+1210h+var_1198], eax
0x1800a4c66  mov     eax, [rbp+10D0h+arg_58]
0x1800a4c6c  mov     [rsp+1210h+var_11A0], eax
0x1800a4c70  mov     eax, [rbp+10D0h+var_1140]
0x1800a4c73  mov     [rsp+1210h+var_11A8], eax
0x1800a4c77  mov     r13d, [rbp+10D0h+var_114C]
0x1800a4c7b  mov     [rsp+1210h+var_11B0], r13d
0x1800a4c80  mov     eax, [rbp+10D0h+var_113C]
0x1800a4c83  mov     [rsp+1210h+var_11B8], eax
0x1800a4c87  mov     [rsp+1210h+var_11C0], r12d
0x1800a4c8c  mov     eax, [rbp+10D0h+arg_38]
0x1800a4c92  mov     [rsp+1210h+var_11C8], eax
0x1800a4c96  mov     eax, [rbp+10D0h+arg_30]
0x1800a4c9c  mov     [rsp+1210h+var_11D0], eax
0x1800a4ca0  mov     eax, [rbp+10D0h+arg_28]
0x1800a4ca6  mov     [rsp+1210h+var_11D8], eax
0x1800a4caa  mov     eax, [rbp+10D0h+arg_20]
0x1800a4cb0  mov     [rsp+1210h+var_11E0], eax
0x1800a4cb4  mov     [rsp+1210h+var_11E8], rcx
0x1800a4cb9  mov     rax, [rbp+10D0h+var_1118]
0x1800a4cbd  mov     [rsp+1210h+var_11F0], rax
0x1800a4cc2  mov     r9, [rbp+10D0h+var_1110]
0x1800a4cc6  lea     rdx, aSessionNameLsS; "\tsession-name: %ls\n\tserver-name: %ls"...
0x1800a4ccd  mov     rcx, [rdi+60h]; Stream
0x1800a4cd1  call    fwprintf
0x1800a4cd6  test    eax, eax
0x1800a4cd8  js      loc_1800A4A7E
0x1800a4cde  lea     rdx, asc_1800C9780; "}\n"
0x1800a4ce5  mov     rcx, [rdi+60h]; Stream
0x1800a4ce9  call    fwprintf
0x1800a4cee  test    eax, eax
0x1800a4cf0  jns     short loc_1800A4CFB
0x1800a4cf2  jmp     loc_1800A4A7E
0x1800a4cf7  mov     r13d, [rbp+10D0h+var_114C]
0x1800a4cfb  mov     rcx, [rdi+58h]; Stream
0x1800a4cff  test    rcx, rcx
0x1800a4d02  jz      loc_1800A4F11
0x1800a4d08  xor     r8d, r8d; Origin
0x1800a4d0b  xor     edx, edx; Offset
0x1800a4d0d  call    cs:__imp_fseek
0x1800a4d14  nop     dword ptr [rax+rax+00h]
0x1800a4d19  test    eax, eax
0x1800a4d1b  jnz     loc_1800A4A7E
0x1800a4d21  mov     r9, [rdi+58h]; Stream
0x1800a4d25  mov     r8, rbx; ElementCount
0x1800a4d28  lea     edx, [rax+50h]; ElementSize
0x1800a4d2b  lea     rcx, [rbp+10D0h+Buffer]; Buffer
0x1800a4d2f  call    cs:__imp_fread
0x1800a4d36  nop     dword ptr [rax+rax+00h]
0x1800a4d3b  test    eax, eax
0x1800a4d3d  jnz     short loc_1800A4D80
0x1800a4d3f  xor     edx, edx; Val
0x1800a4d41  lea     r8d, [rax+50h]; Size
0x1800a4d45  lea     rcx, [rbp+10D0h+var_10F0]; void *
0x1800a4d49  call    memset_0
0x1800a4d4e  movaps  xmm0, [rbp+10D0h+var_10F0]
0x1800a4d52  movaps  [rbp+10D0h+Buffer], xmm0
0x1800a4d56  movaps  xmm1, [rbp+10D0h+var_10E0]
0x1800a4d5a  movaps  [rbp+10D0h+var_1090], xmm1
0x1800a4d5e  movaps  xmm0, [rbp+10D0h+var_10D0]
0x1800a4d62  movaps  [rbp+10D0h+var_1080], xmm0
0x1800a4d66  movaps  xmm1, [rbp+10D0h+var_10C0]
0x1800a4d6a  movaps  [rbp+10D0h+var_1070], xmm1
0x1800a4d6e  movaps  xmm0, [rbp+10D0h+var_10B0]
0x1800a4d72  movaps  [rbp+10D0h+var_1060], xmm0
0x1800a4d76  mov     eax, 3
0x1800a4d7b  mov     dword ptr [rbp+10D0h+Buffer], eax
0x1800a4d7e  jmp     short loc_1800A4D8B
0x1800a4d80  cmp     eax, ebx
0x1800a4d82  jnz     loc_1800A4A7E
0x1800a4d88  mov     eax, dword ptr [rbp+10D0h+Buffer]
0x1800a4d8b  cmp     eax, 3
0x1800a4d8e  jnz     loc_1800A4ED2
0x1800a4d94  mov     rcx, qword ptr [rbp+10D0h+Buffer+8]
0x1800a4d98  shr     rcx, 20h
0x1800a4d9c  lea     r8d, [rcx+1]
0x1800a4da0  mov     eax, ecx
0x1800a4da2  imul    eax, dword ptr [rbp+10D0h+Buffer+4]
0x1800a4da6  add     eax, [rbp+10D0h+arg_20]
0x1800a4dac  xor     edx, edx
0x1800a4dae  div     r8d
0x1800a4db1  mov     dword ptr [rbp+10D0h+Buffer+4], eax
0x1800a4db4  imul    ecx, dword ptr [rbp+10D0h+Buffer+8]
0x1800a4db8  add     ecx, [rbp+10D0h+arg_28]
0x1800a4dbe  xor     edx, edx
0x1800a4dc0  mov     eax, ecx
0x1800a4dc2  div     r8d
0x1800a4dc5  mov     dword ptr [rbp+10D0h+Buffer+8], eax
0x1800a4dc8  mov     dword ptr [rbp+10D0h+Buffer+0Ch], r8d
0x1800a4dcc  test    r12d, r12d
0x1800a4dcf  jz      short loc_1800A4E35
0x1800a4dd1  mov     r8d, dword ptr [rbp+10D0h+var_1080]
0x1800a4dd5  lea     r9d, [r8+1]
0x1800a4dd9  mov     eax, r8d
0x1800a4ddc  imul    eax, dword ptr [rbp+10D0h+var_1090]
0x1800a4de0  add     eax, r12d
0x1800a4de3  xor     edx, edx
0x1800a4de5  div     r9d
0x1800a4de8  mov     dword ptr [rbp+10D0h+var_1090], eax
0x1800a4deb  test    r14, r14
0x1800a4dee  jz      short loc_1800A4E07
0x1800a4df0  mov     eax, dword ptr [rbp+10D0h+var_1080+4]
0x1800a4df3  lea     ecx, [rax+1]
0x1800a4df6  imul    eax, dword ptr [rbp+10D0h+var_1090+4]
0x1800a4dfa  add     eax, r13d
0x1800a4dfd  xor     edx, edx
0x1800a4dff  div     ecx
0x1800a4e01  mov     dword ptr [rbp+10D0h+var_1090+4], eax
0x1800a4e04  mov     dword ptr [rbp+10D0h+var_1080+4], ecx
0x1800a4e07  mov     eax, dword ptr [rbp+10D0h+var_1090+8]
0x1800a4e0a  imul    eax, r8d
0x1800a4e0e  add     eax, [rbp+10D0h+arg_58]
0x1800a4e14  xor     edx, edx
0x1800a4e16  div     r9d
0x1800a4e19  mov     dword ptr [rbp+10D0h+var_1090+8], eax
0x1800a4e1c  mov     eax, dword ptr [rbp+10D0h+var_1090+0Ch]
0x1800a4e1f  imul    eax, r8d
0x1800a4e23  add     eax, [rbp+10D0h+arg_38]
0x1800a4e29  xor     edx, edx
0x1800a4e2b  div     r9d
0x1800a4e2e  mov     dword ptr [rbp+10D0h+var_1090+0Ch], eax
0x1800a4e31  mov     dword ptr [rbp+10D0h+var_1080], r9d
0x1800a4e35  test    r15d, r15d
  ... truncated ...
```
