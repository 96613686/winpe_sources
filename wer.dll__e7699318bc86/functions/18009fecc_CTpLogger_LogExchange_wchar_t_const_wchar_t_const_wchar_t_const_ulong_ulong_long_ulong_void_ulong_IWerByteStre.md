# CTpLogger::LogExchange(wchar_t const *,wchar_t const *,wchar_t const *,ulong,ulong,long,ulong,void *,ulong,IWerByteStream *,ulong,long,ulong,ulong,long,ulong,void *,ulong,ulong,wchar_t const *)

- ea: `0x18009fecc`
- end: `0x1800a0461`
- name: `?LogExchange@CTpLogger@@QEAAJPEB_W00KKJKPEAXKPEAUIWerByteStream@@KJKKJK1KK0@Z`
- size: `1429`
- prototype: `__int64 __fastcall(CTpLogger *__hidden this, const wchar_t *, const wchar_t *, const wchar_t *, unsigned int, unsigned int, int, unsigned int, void *, unsigned int, struct IWerByteStream *, unsigned int, int, unsigned int, unsigned int, int, unsigned int, void *, unsigned int, unsigned int, const wchar_t *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003c24c`

## callees

- `0x180015520`
- `0x180050db0`
- `0x1800517cc`
- `0x1800517d8`
- `0x18009fecc`
- `0x1800aa000`
- `0x1800ad010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_fread` at `0x1800a0261`
- `api-ms-win-crt-private-l1-1-0!_o_fread` at `0x1800a0261`
- `api-ms-win-crt-private-l1-1-0!_o_fseek` at `0x1800a0245`
- `api-ms-win-crt-private-l1-1-0!_o_fseek` at `0x1800a0407`
- `api-ms-win-crt-private-l1-1-0!_o_fseek` at `0x1800a0245`
- `api-ms-win-crt-private-l1-1-0!_o_fseek` at `0x1800a0407`
- `api-ms-win-crt-private-l1-1-0!_o_fwrite` at `0x18009ffb8`
- `api-ms-win-crt-private-l1-1-0!_o_fwrite` at `0x1800a0063`
- `api-ms-win-crt-private-l1-1-0!_o_fwrite` at `0x1800a00d3`
- `api-ms-win-crt-private-l1-1-0!_o_fwrite` at `0x1800a0423`
- `api-ms-win-crt-private-l1-1-0!_o_fwrite` at `0x18009ffb8`
- `api-ms-win-crt-private-l1-1-0!_o_fwrite` at `0x1800a0063`
- `api-ms-win-crt-private-l1-1-0!_o_fwrite` at `0x1800a00d3`
- `api-ms-win-crt-private-l1-1-0!_o_fwrite` at `0x1800a0423`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009ff6c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009ff6c`

## string_xrefs

- `0x1800a01fe`: `	session-name: %ls\n	server-name: %ls\n	request-url: %ls\n	exchange-name: %ls\n	connect-time: %u\n	proxy-resolution-time: %u\n	xml-write-rc: %08X\n	xml-write-time: %u\n	send-xml-size: %u\n	send-xml-log-offset: %08X\n	send-bin-size: %u\n	send-bin-log-offset: %08X\n	send-time: %u\n	xml-parse-rc: %08X\n	xml-parse-time: %u\n	msft-root-check-time: %u\n	net-result-rc: %08X\n	receive-http-code: %u\n	receive-size: %u\n	receive-time: %u\n	receive-log-offset: %08X\n	headers: %ls\n`

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
  utl::unique_lock<utl::recursive_mutex>::~unique_lock<utl::recursive_mutex>((__int64)&v51);
  return v25;
}

```

## disassembly

```asm
0x18009fecc  push    rbp
0x18009fece  push    rbx
0x18009fecf  push    rsi
0x18009fed0  push    rdi
0x18009fed1  push    r12
0x18009fed3  push    r13
0x18009fed5  push    r14
0x18009fed7  push    r15
0x18009fed9  lea     rbp, [rsp-1098h]
0x18009fee1  mov     eax, 11D8h
0x18009fee6  call    _alloca_probe
0x18009feeb  sub     rsp, rax
0x18009feee  mov     rax, cs:__security_cookie
0x18009fef5  xor     rax, rsp
0x18009fef8  mov     [rbp+10D0h+var_50], rax
0x18009feff  mov     [rbp+10D0h+var_1120], r9
0x18009ff03  mov     [rbp+10D0h+var_1118], r8
0x18009ff07  mov     [rbp+10D0h+var_1110], rdx
0x18009ff0b  mov     rdi, rcx
0x18009ff0e  mov     rax, [rbp+10D0h+arg_A0]
0x18009ff15  mov     [rbp+10D0h+var_1128], rax
0x18009ff19  mov     r13, [rbp+10D0h+arg_40]
0x18009ff20  mov     r14, [rbp+10D0h+arg_50]
0x18009ff27  mov     rax, [rbp+10D0h+arg_88]
0x18009ff2e  mov     [rbp+10D0h+var_1130], rax
0x18009ff32  xor     edx, edx; Val
0x18009ff34  lea     r8d, [rdx+50h]; Size
0x18009ff38  lea     rcx, [rbp+10D0h+Buffer]; void *
0x18009ff3c  call    memset_0
0x18009ff41  cmp     dword ptr [rdi+7Ch], 0
0x18009ff45  jnz     short loc_18009FF51
0x18009ff47  mov     eax, 1
0x18009ff4c  jmp     loc_1800A043E
0x18009ff51  or      eax, 0FFFFFFFFh
0x18009ff54  mov     [rbp+10D0h+var_113C], eax
0x18009ff57  mov     [rbp+10D0h+var_1140], eax
0x18009ff5a  mov     [rbp+10D0h+var_114C], 0
0x18009ff61  mov     [rbp+10D0h+var_1144], eax
0x18009ff64  lea     rcx, [rdi+8]; lpCriticalSection
0x18009ff68  mov     [rbp+10D0h+var_1108], rcx
0x18009ff6c  call    cs:__imp_EnterCriticalSection
0x18009ff72  mov     ebx, 1
0x18009ff77  mov     [rbp+10D0h+var_1100], bl
0x18009ff7a  mov     edx, [rdi+70h]
0x18009ff7d  mov     [rbp+10D0h+var_1148], edx
0x18009ff80  lea     eax, [rdx+1]
0x18009ff83  mov     [rdi+70h], eax
0x18009ff86  mov     r9, [rdi+68h]
0x18009ff8a  mov     r15d, [rbp+10D0h+arg_90]
0x18009ff91  mov     r12d, [rbp+10D0h+arg_48]
0x18009ff98  test    r9, r9
0x18009ff9b  jz      loc_1800A00EC
0x18009ffa1  lea     rsi, [rdi+74h]
0x18009ffa5  test    r12d, r12d
0x18009ffa8  jz      short loc_18009FFCF
0x18009ffaa  mov     eax, [rsi]
0x18009ffac  mov     [rbp+10D0h+var_113C], eax
0x18009ffaf  mov     edx, r12d
0x18009ffb2  mov     r8d, ebx
0x18009ffb5  mov     rcx, r13
0x18009ffb8  call    cs:__imp__o_fwrite
0x18009ffbe  cmp     eax, ebx
0x18009ffc0  jz      short loc_18009FFCC
0x18009ffc2  mov     ebx, 80004005h
0x18009ffc7  jmp     loc_1800A0433
0x18009ffcc  add     [rsi], r12d
0x18009ffcf  cmp     dword ptr [rdi+80h], 0
0x18009ffd6  jz      loc_1800A00BD
0x18009ffdc  test    r14, r14
0x18009ffdf  jz      loc_1800A00BD
0x18009ffe5  mov     [rbp+10D0h+var_1150], 0
0x18009ffec  mov     [rbp+10D0h+var_1138], 0
0x18009fff4  mov     rax, [r14]
0x18009fff7  lea     r9, [rbp+10D0h+var_1138]
0x18009fffb  xor     r8d, r8d
0x18009fffe  xor     edx, edx
0x1800a0000  mov     rcx, r14
0x1800a0003  mov     rax, [rax+10h]
0x1800a0007  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a000c  test    eax, eax
0x1800a000e  js      loc_1800A00BD
0x1800a0014  lea     rsi, [rdi+74h]
0x1800a0018  mov     eax, [rsi]
0x1800a001a  mov     [rbp+10D0h+var_1140], eax
0x1800a001d  xor     r13d, r13d
0x1800a0020  mov     [rbp+10D0h+var_114C], r13d
0x1800a0024  mov     rax, [r14]
0x1800a0027  mov     [rsp+1210h+var_11F0], r13
0x1800a002c  lea     r9, [rbp+10D0h+var_1150]
0x1800a0030  mov     r8d, 1000h
0x1800a0036  lea     rdx, [rbp+10D0h+var_1050]
0x1800a003d  mov     rcx, r14
0x1800a0040  mov     rax, [rax]
0x1800a0043  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a0048  test    eax, eax
0x1800a004a  js      short loc_1800A00A5
0x1800a004c  mov     eax, [rbp+10D0h+var_1150]
0x1800a004f  test    eax, eax
0x1800a0051  jz      short loc_1800A00A1
0x1800a0053  mov     edx, eax
0x1800a0055  mov     r9, [rdi+68h]
0x1800a0059  mov     r8, rbx
0x1800a005c  lea     rcx, [rbp+10D0h+var_1050]
0x1800a0063  call    cs:__imp__o_fwrite
0x1800a0069  cmp     eax, ebx
0x1800a006b  jnz     short loc_1800A00A1
0x1800a006d  mov     eax, [rbp+10D0h+var_1150]
0x1800a0070  add     [rsi], eax
0x1800a0072  add     r13d, eax
0x1800a0075  mov     rax, [r14]
0x1800a0078  mov     [rsp+1210h+var_11F0], 0
0x1800a0081  lea     r9, [rbp+10D0h+var_1150]
0x1800a0085  mov     r8d, 1000h
0x1800a008b  lea     rdx, [rbp+10D0h+var_1050]
0x1800a0092  mov     rcx, r14
0x1800a0095  mov     rax, [rax]
0x1800a0098  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a009d  test    eax, eax
0x1800a009f  jns     short loc_1800A004C
0x1800a00a1  mov     [rbp+10D0h+var_114C], r13d
0x1800a00a5  mov     rax, [r14]
0x1800a00a8  mov     edx, dword ptr [rbp+10D0h+var_1138]
0x1800a00ab  xor     r9d, r9d
0x1800a00ae  xor     r8d, r8d
0x1800a00b1  mov     rcx, r14
0x1800a00b4  mov     rax, [rax+10h]
0x1800a00b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a00bd  test    r15d, r15d
0x1800a00c0  jz      short loc_1800A00E9
0x1800a00c2  mov     r13d, [rsi]
0x1800a00c5  mov     rdx, r15
0x1800a00c8  mov     r9, [rdi+68h]
0x1800a00cc  mov     r8, rbx
0x1800a00cf  mov     rcx, [rbp+10D0h+var_1130]
0x1800a00d3  call    cs:__imp__o_fwrite
0x1800a00d9  cmp     eax, ebx
0x1800a00db  jnz     loc_18009FFC2
0x1800a00e1  add     [rsi], r15d
0x1800a00e4  mov     edx, [rbp+10D0h+var_1148]
0x1800a00e7  jmp     short loc_1800A00F0
0x1800a00e9  mov     edx, [rbp+10D0h+var_1148]
0x1800a00ec  mov     r13d, [rbp+10D0h+var_1144]
0x1800a00f0  mov     rcx, [rdi+60h]; Stream
0x1800a00f4  mov     esi, [rbp+10D0h+arg_70]
0x1800a00fa  test    rcx, rcx
0x1800a00fd  jz      loc_1800A022F
0x1800a0103  mov     r8d, edx
0x1800a0106  lea     rdx, aExchangeU; "exchange %u {\n"
0x1800a010d  call    fwprintf
0x1800a0112  test    eax, eax
0x1800a0114  js      loc_18009FFC2
0x1800a011a  lea     r8, aNone; "none"
0x1800a0121  mov     rax, [rbp+10D0h+var_1128]
0x1800a0125  test    rax, rax
0x1800a0128  cmovz   rax, r8
0x1800a012c  mov     rcx, [rbp+10D0h+var_1120]
0x1800a0130  test    rcx, rcx
0x1800a0133  cmovz   rcx, r8
0x1800a0137  cmp     qword ptr [rdi+50h], 0
0x1800a013c  cmovnz  r8, [rdi+50h]
0x1800a0141  mov     [rsp+1210h+var_1158], rax
0x1800a0149  mov     [rsp+1210h+var_1160], r13d
0x1800a0151  mov     eax, [rbp+10D0h+arg_98]
0x1800a0157  mov     [rsp+1210h+var_1168], eax
0x1800a015e  mov     [rsp+1210h+var_1170], r15d
0x1800a0166  mov     eax, [rbp+10D0h+arg_80]
0x1800a016c  mov     [rsp+1210h+var_1178], eax
0x1800a0173  mov     eax, [rbp+10D0h+arg_78]
0x1800a0179  mov     [rsp+1210h+var_1180], eax
0x1800a0180  mov     [rsp+1210h+var_1188], esi
0x1800a0187  mov     eax, [rbp+10D0h+arg_68]
0x1800a018d  mov     [rsp+1210h+var_1190], eax
0x1800a0194  mov     eax, [rbp+10D0h+arg_60]
0x1800a019a  mov     [rsp+1210h+var_1198], eax
0x1800a019e  mov     eax, [rbp+10D0h+arg_58]
0x1800a01a4  mov     [rsp+1210h+var_11A0], eax
0x1800a01a8  mov     eax, [rbp+10D0h+var_1140]
0x1800a01ab  mov     [rsp+1210h+var_11A8], eax
0x1800a01af  mov     r13d, [rbp+10D0h+var_114C]
0x1800a01b3  mov     [rsp+1210h+var_11B0], r13d
0x1800a01b8  mov     eax, [rbp+10D0h+var_113C]
0x1800a01bb  mov     [rsp+1210h+var_11B8], eax
0x1800a01bf  mov     [rsp+1210h+var_11C0], r12d
0x1800a01c4  mov     eax, [rbp+10D0h+arg_38]
0x1800a01ca  mov     [rsp+1210h+var_11C8], eax
0x1800a01ce  mov     eax, [rbp+10D0h+arg_30]
0x1800a01d4  mov     [rsp+1210h+var_11D0], eax
0x1800a01d8  mov     eax, [rbp+10D0h+arg_28]
0x1800a01de  mov     [rsp+1210h+var_11D8], eax
0x1800a01e2  mov     eax, [rbp+10D0h+arg_20]
0x1800a01e8  mov     [rsp+1210h+var_11E0], eax
0x1800a01ec  mov     [rsp+1210h+var_11E8], rcx
0x1800a01f1  mov     rax, [rbp+10D0h+var_1118]
0x1800a01f5  mov     [rsp+1210h+var_11F0], rax
0x1800a01fa  mov     r9, [rbp+10D0h+var_1110]
0x1800a01fe  lea     rdx, aSessionNameLsS; "\tsession-name: %ls\n\tserver-name: %ls"...
0x1800a0205  mov     rcx, [rdi+60h]; Stream
0x1800a0209  call    fwprintf
0x1800a020e  test    eax, eax
0x1800a0210  js      loc_18009FFC2
0x1800a0216  lea     rdx, asc_1800C4700; "}\n"
0x1800a021d  mov     rcx, [rdi+60h]; Stream
0x1800a0221  call    fwprintf
0x1800a0226  test    eax, eax
0x1800a0228  jns     short loc_1800A0233
0x1800a022a  jmp     loc_18009FFC2
0x1800a022f  mov     r13d, [rbp+10D0h+var_114C]
0x1800a0233  mov     rcx, [rdi+58h]; Stream
0x1800a0237  test    rcx, rcx
0x1800a023a  jz      loc_1800A0431
0x1800a0240  xor     r8d, r8d; Origin
0x1800a0243  xor     edx, edx; Offset
0x1800a0245  call    cs:__imp_fseek
0x1800a024b  test    eax, eax
0x1800a024d  jnz     loc_18009FFC2
0x1800a0253  mov     r9, [rdi+58h]; Stream
0x1800a0257  mov     r8, rbx; ElementCount
0x1800a025a  lea     edx, [rax+50h]; ElementSize
0x1800a025d  lea     rcx, [rbp+10D0h+Buffer]; Buffer
0x1800a0261  call    cs:__imp_fread
0x1800a0267  test    eax, eax
0x1800a0269  jnz     short loc_1800A02AC
0x1800a026b  xor     edx, edx; Val
0x1800a026d  lea     r8d, [rax+50h]; Size
0x1800a0271  lea     rcx, [rbp+10D0h+var_10F0]; void *
0x1800a0275  call    memset_0
0x1800a027a  movaps  xmm0, [rbp+10D0h+var_10F0]
0x1800a027e  movaps  [rbp+10D0h+Buffer], xmm0
0x1800a0282  movaps  xmm1, [rbp+10D0h+var_10E0]
0x1800a0286  movaps  [rbp+10D0h+var_1090], xmm1
0x1800a028a  movaps  xmm0, [rbp+10D0h+var_10D0]
0x1800a028e  movaps  [rbp+10D0h+var_1080], xmm0
0x1800a0292  movaps  xmm1, [rbp+10D0h+var_10C0]
0x1800a0296  movaps  [rbp+10D0h+var_1070], xmm1
0x1800a029a  movaps  xmm0, [rbp+10D0h+var_10B0]
0x1800a029e  movaps  [rbp+10D0h+var_1060], xmm0
0x1800a02a2  mov     eax, 3
0x1800a02a7  mov     dword ptr [rbp+10D0h+Buffer], eax
0x1800a02aa  jmp     short loc_1800A02B7
0x1800a02ac  cmp     eax, ebx
0x1800a02ae  jnz     loc_18009FFC2
0x1800a02b4  mov     eax, dword ptr [rbp+10D0h+Buffer]
0x1800a02b7  cmp     eax, 3
0x1800a02ba  jnz     loc_1800A03FE
0x1800a02c0  mov     rcx, qword ptr [rbp+10D0h+Buffer+8]
0x1800a02c4  shr     rcx, 20h
0x1800a02c8  lea     r8d, [rcx+1]
0x1800a02cc  mov     eax, ecx
0x1800a02ce  imul    eax, dword ptr [rbp+10D0h+Buffer+4]
0x1800a02d2  add     eax, [rbp+10D0h+arg_20]
0x1800a02d8  xor     edx, edx
0x1800a02da  div     r8d
0x1800a02dd  mov     dword ptr [rbp+10D0h+Buffer+4], eax
0x1800a02e0  imul    ecx, dword ptr [rbp+10D0h+Buffer+8]
0x1800a02e4  add     ecx, [rbp+10D0h+arg_28]
0x1800a02ea  xor     edx, edx
0x1800a02ec  mov     eax, ecx
0x1800a02ee  div     r8d
0x1800a02f1  mov     dword ptr [rbp+10D0h+Buffer+8], eax
0x1800a02f4  mov     dword ptr [rbp+10D0h+Buffer+0Ch], r8d
0x1800a02f8  test    r12d, r12d
0x1800a02fb  jz      short loc_1800A0361
0x1800a02fd  mov     r8d, dword ptr [rbp+10D0h+var_1080]
0x1800a0301  lea     r9d, [r8+1]
0x1800a0305  mov     eax, r8d
0x1800a0308  imul    eax, dword ptr [rbp+10D0h+var_1090]
0x1800a030c  add     eax, r12d
0x1800a030f  xor     edx, edx
0x1800a0311  div     r9d
0x1800a0314  mov     dword ptr [rbp+10D0h+var_1090], eax
0x1800a0317  test    r14, r14
0x1800a031a  jz      short loc_1800A0333
0x1800a031c  mov     eax, dword ptr [rbp+10D0h+var_1080+4]
0x1800a031f  lea     ecx, [rax+1]
0x1800a0322  imul    eax, dword ptr [rbp+10D0h+var_1090+4]
0x1800a0326  add     eax, r13d
0x1800a0329  xor     edx, edx
0x1800a032b  div     ecx
0x1800a032d  mov     dword ptr [rbp+10D0h+var_1090+4], eax
0x1800a0330  mov     dword ptr [rbp+10D0h+var_1080+4], ecx
0x1800a0333  mov     eax, dword ptr [rbp+10D0h+var_1090+8]
0x1800a0336  imul    eax, r8d
0x1800a033a  add     eax, [rbp+10D0h+arg_58]
0x1800a0340  xor     edx, edx
0x1800a0342  div     r9d
0x1800a0345  mov     dword ptr [rbp+10D0h+var_1090+8], eax
0x1800a0348  mov     eax, dword ptr [rbp+10D0h+var_1090+0Ch]
0x1800a034b  imul    eax, r8d
0x1800a034f  add     eax, [rbp+10D0h+arg_38]
0x1800a0355  xor     edx, edx
0x1800a0357  div     r9d
0x1800a035a  mov     dword ptr [rbp+10D0h+var_1090+0Ch], eax
0x1800a035d  mov     dword ptr [rbp+10D0h+var_1080], r9d
0x1800a0361  test    r15d, r15d
0x1800a0364  jz      short loc_1800A03AA
0x1800a0366  mov     ecx, dword ptr [rbp+10D0h+var_1070+4]
0x1800a0369  lea     r8d, [rcx+1]
0x1800a036d  mov     eax, ecx
0x1800a036f  imul    eax, dword ptr [rbp+10D0h+var_1080+8]
0x1800a0373  add     eax, r15d
  ... truncated ...
```
