# LOG_WRITER::UpdateHeaders(void)

- ea: `0x180005f04`
- end: `0x180006141`
- name: `?UpdateHeaders@LOG_WRITER@@AEAAJXZ`
- size: `573`
- prototype: `__int64 __fastcall(LOG_WRITER *__hidden this)`
- caller_count: `2`
- callee_count: `6`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180004fe4`
- `0x180005ccc`

## callees

- `0x180002704`
- `0x180002eb8`
- `0x180002f48`
- `0x180005f04`
- `0x18000e97a`
- `0x18000e9a0`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x180005f87`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x180005f87`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000610e`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000610e`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180005f59`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180005f59`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180005f7c`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180005fd5`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180006008`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180006024`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x1800060c2`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180005f7c`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180005fd5`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180006008`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180006024`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x1800060c2`
- `iisutil!?AppendWSimple@STRA@@QEAAJPEBGK@Z` at `0x180006101`
- `iisutil!?AppendWSimple@STRA@@QEAAJPEBGK@Z` at `0x180006101`
- `iisutil!?CopyWToUTF8Unescaped@STRA@@QEAAJAEBVSTRU@@@Z` at `0x1800060ef`
- `iisutil!?CopyWToUTF8Unescaped@STRA@@QEAAJAEBVSTRU@@@Z` at `0x1800060ef`

## string_xrefs

- `0x180005f70`: `#Software: Microsoft Internet Information Services 10.0\n#Version: 1.0\n#Date: `

## pseudocode

```c
__int64 __fastcall LOG_WRITER::UpdateHeaders(LOG_WRITER *this)
{
  __int64 v2; // r14
  LOG_WRITER *v3; // rcx
  LOG_WRITER *v4; // rcx
  int appended; // ebx
  int i; // edi
  LOG_WRITER *v7; // rcx
  unsigned __int16 *v8; // rdi
  __int64 v9; // r9
  __int64 v10; // rax
  __int64 v11; // r9
  STRA *v12; // rcx
  int v13; // eax
  _BYTE v15[32]; // [rsp+30h] [rbp-D0h] BYREF
  const unsigned __int16 *v16; // [rsp+50h] [rbp-B0h]
  unsigned int v17; // [rsp+58h] [rbp-A8h]
  unsigned int v18; // [rsp+60h] [rbp-A0h]
  struct _SYSTEMTIME SystemTime; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int16 v20[256]; // [rsp+80h] [rbp-80h] BYREF

  memset_0(v20, 0, sizeof(v20));
  STRU::STRU((STRU *)v15, v20, 0x100u);
  SystemTime = 0;
  v2 = *(unsigned int *)(*((_QWORD *)this + 1) + 16LL);
  STRU::Append((STRU *)v15, L"#Software: Microsoft Internet Information Services 10.0\r\n#Version: 1.0\r\n#Date: ");
  GetSystemTime(&SystemTime);
  appended = LOG_WRITER::AppendDate(v3, (struct STRU *)v15, &SystemTime);
  if ( appended >= 0 )
  {
    appended = LOG_WRITER::AppendTime(v4, (struct STRU *)v15, &SystemTime, L"\r\n");
    if ( appended >= 0 )
    {
      appended = STRU::Append((STRU *)v15, L"#Fields: ");
      if ( appended >= 0 )
      {
        for ( i = 0; i < 22; ++i )
        {
          if ( (v2 & (unsigned __int64)(&LOG_WRITER::sm_httpSysHeaderMap)[i]) != 0 )
          {
            appended = STRU::Append((STRU *)v15, (const unsigned __int16 *)(&LOG_WRITER::sm_httpSysHeaders)[i]);
            if ( appended < 0 )
              goto LABEL_23;
            STRU::Append((STRU *)v15, L" ");
          }
        }
        v7 = *(LOG_WRITER **)(*((_QWORD *)this + 1) + 192LL);
        v8 = (unsigned __int16 *)((unsigned __int64)v7 & -(__int64)(*(_WORD *)v7 != 0));
        if ( v8 )
        {
          while ( 1 )
          {
            v9 = -1;
            do
              ++v9;
            while ( v8[v9] );
            appended = LOG_WRITER::AppendStringReplaceSpaces(v7, (struct STRU *)v15, v8, v9, 0x2Du);
            if ( appended < 0 )
              break;
            v10 = -1;
            do
              ++v10;
            while ( v8[v10] );
            v8 += v10 + 1;
            if ( !*v8 )
              goto LABEL_16;
          }
        }
        else
        {
LABEL_16:
          v11 = v18 - 1;
          if ( (unsigned int)v11 < v17 >> 1 )
          {
            v16[v11] = 0;
            v18 = v11;
          }
          appended = STRU::Append((STRU *)v15, L"\r\n");
          if ( appended >= 0 )
          {
            v12 = (LOG_WRITER *)((char *)this + 184);
            **((_BYTE **)this + 27) = 0;
            *((_DWORD *)this + 58) = 0;
            if ( *(_DWORD *)(*((_QWORD *)this + 1) + 12LL) )
              v13 = STRA::CopyWToUTF8Unescaped(v12, (const struct STRU *)v15);
            else
              v13 = STRA::AppendWSimple(v12, v16, v18);
            appended = v13;
          }
        }
      }
    }
  }
LABEL_23:
  STRU::~STRU((STRU *)v15);
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x180005f04  mov     [rsp-8+arg_8], rbx
0x180005f09  mov     [rsp-8+arg_10], rsi
0x180005f0e  push    rbp
0x180005f0f  push    rdi
0x180005f10  push    r12
0x180005f12  push    r14
0x180005f14  push    r15
0x180005f16  lea     rbp, [rsp-190h]
0x180005f1e  sub     rsp, 290h
0x180005f25  mov     rax, cs:__security_cookie
0x180005f2c  xor     rax, rsp
0x180005f2f  mov     [rbp+1B0h+var_30], rax
0x180005f36  mov     rsi, rcx
0x180005f39  xor     edx, edx; Val
0x180005f3b  mov     r8d, 200h; Size
0x180005f41  lea     rcx, [rbp+1B0h+var_230]; void *
0x180005f45  call    memset_0
0x180005f4a  mov     r8d, 100h
0x180005f50  lea     rdx, [rbp+1B0h+var_230]
0x180005f54  lea     rcx, [rsp+2B0h+var_280]
0x180005f59  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180005f5f  nop
0x180005f60  xorps   xmm0, xmm0
0x180005f63  movups  xmmword ptr [rsp+2B0h+SystemTime.wYear], xmm0
0x180005f68  mov     rax, [rsi+8]
0x180005f6c  mov     r14d, [rax+10h]
0x180005f70  lea     rdx, aSoftwareMicros; "#Software: Microsoft Internet Informati"...
0x180005f77  lea     rcx, [rsp+2B0h+var_280]
0x180005f7c  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180005f82  lea     rcx, [rsp+2B0h+SystemTime]; lpSystemTime
0x180005f87  call    cs:__imp_GetSystemTime
0x180005f8d  lea     r8, [rsp+2B0h+SystemTime]; struct _SYSTEMTIME *
0x180005f92  lea     rdx, [rsp+2B0h+var_280]; struct STRU *
0x180005f97  call    ?AppendDate@LOG_WRITER@@AEAAJPEAVSTRU@@PEAU_SYSTEMTIME@@@Z; LOG_WRITER::AppendDate(STRU *,_SYSTEMTIME *)
0x180005f9c  mov     ebx, eax
0x180005f9e  xor     r15d, r15d
0x180005fa1  test    eax, eax
0x180005fa3  js      loc_180006109
0x180005fa9  lea     r9, asc_1800120D0; "\r\n"
0x180005fb0  lea     r8, [rsp+2B0h+SystemTime]; struct _SYSTEMTIME *
0x180005fb5  lea     rdx, [rsp+2B0h+var_280]; struct STRU *
0x180005fba  call    ?AppendTime@LOG_WRITER@@AEAAJPEAVSTRU@@PEAU_SYSTEMTIME@@PEBG@Z; LOG_WRITER::AppendTime(STRU *,_SYSTEMTIME *,ushort const *)
0x180005fbf  mov     ebx, eax
0x180005fc1  test    eax, eax
0x180005fc3  js      loc_180006109
0x180005fc9  lea     rdx, aFields; "#Fields: "
0x180005fd0  lea     rcx, [rsp+2B0h+var_280]
0x180005fd5  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180005fdb  mov     ebx, eax
0x180005fdd  test    eax, eax
0x180005fdf  js      loc_180006109
0x180005fe5  mov     edi, r15d
0x180005fe8  lea     r12, cs:180000000h
0x180005fef  mov     edx, edi
0x180005ff1  test    ds:rva ?sm_httpSysHeaderMap@LOG_WRITER@@0PA_KA[r12+rdx*8], r14; unsigned __int64 near * LOG_WRITER::sm_httpSysHeaderMap ...
0x180005ff9  jbe     short loc_18000602A
0x180005ffb  mov     rdx, ds:rva ?sm_httpSysHeaders@LOG_WRITER@@0PAPEAGA[r12+rdx*8]; ushort * near * LOG_WRITER::sm_httpSysHeaders ...
0x180006003  lea     rcx, [rsp+2B0h+var_280]
0x180006008  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x18000600e  mov     ebx, eax
0x180006010  test    eax, eax
0x180006012  js      loc_180006109
0x180006018  lea     rdx, asc_180012138; " "
0x18000601f  lea     rcx, [rsp+2B0h+var_280]
0x180006024  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x18000602a  inc     edi
0x18000602c  cmp     edi, 16h
0x18000602f  jl      short loc_180005FEF
0x180006031  mov     rax, [rsi+8]
0x180006035  mov     rcx, [rax+0C0h]; this
0x18000603c  movzx   eax, word ptr [rcx]
0x18000603f  neg     ax
0x180006042  sbb     rdi, rdi
0x180006045  and     rdi, rcx
0x180006048  jz      short loc_180006094
0x18000604a  or      r14, 0FFFFFFFFFFFFFFFFh
0x18000604e  mov     r9, r14
0x180006051  inc     r9; unsigned int
0x180006054  cmp     [rdi+r9*2], r15w
0x180006059  jnz     short loc_180006051
0x18000605b  mov     [rsp+2B0h+var_290], 2Dh ; '-'; unsigned __int16
0x180006062  mov     r8, rdi; unsigned __int16 *
0x180006065  lea     rdx, [rsp+2B0h+var_280]; struct STRU *
0x18000606a  call    ?AppendStringReplaceSpaces@LOG_WRITER@@AEAAJPEAVSTRU@@PEBGKG@Z; LOG_WRITER::AppendStringReplaceSpaces(STRU *,ushort const *,ulong,ushort)
0x18000606f  mov     ebx, eax
0x180006071  test    eax, eax
0x180006073  js      loc_180006109
0x180006079  mov     rax, r14
0x18000607c  inc     rax
0x18000607f  cmp     [rdi+rax*2], r15w
0x180006084  jnz     short loc_18000607C
0x180006086  lea     rdi, [rdi+rax*2]
0x18000608a  add     rdi, 2
0x18000608e  cmp     [rdi], r15w
0x180006092  jnz     short loc_18000604E
0x180006094  mov     r9d, [rsp+2B0h+var_250]
0x180006099  dec     r9d
0x18000609c  mov     eax, [rsp+2B0h+var_258]
0x1800060a0  shr     eax, 1
0x1800060a2  cmp     r9d, eax
0x1800060a5  jnb     short loc_1800060B6
0x1800060a7  mov     rax, [rsp+2B0h+var_260]
0x1800060ac  mov     [rax+r9*2], r15w
0x1800060b1  mov     [rsp+2B0h+var_250], r9d
0x1800060b6  lea     rdx, asc_1800120D0; "\r\n"
0x1800060bd  lea     rcx, [rsp+2B0h+var_280]
0x1800060c2  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x1800060c8  mov     ebx, eax
0x1800060ca  test    eax, eax
0x1800060cc  js      short loc_180006109
0x1800060ce  lea     rcx, [rsi+0B8h]
0x1800060d5  mov     rax, [rcx+20h]
0x1800060d9  mov     [rax], r15b
0x1800060dc  mov     [rcx+30h], r15d
0x1800060e0  mov     rax, [rsi+8]
0x1800060e4  cmp     [rax+0Ch], r15d
0x1800060e8  jz      short loc_1800060F7
0x1800060ea  lea     rdx, [rsp+2B0h+var_280]
0x1800060ef  call    cs:__imp_?CopyWToUTF8Unescaped@STRA@@QEAAJAEBVSTRU@@@Z; STRA::CopyWToUTF8Unescaped(STRU const &)
0x1800060f5  jmp     short loc_180006107
0x1800060f7  mov     r8d, [rsp+2B0h+var_250]
0x1800060fc  mov     rdx, [rsp+2B0h+var_260]
0x180006101  call    cs:__imp_?AppendWSimple@STRA@@QEAAJPEBGK@Z; STRA::AppendWSimple(ushort const *,ulong)
0x180006107  mov     ebx, eax
0x180006109  lea     rcx, [rsp+2B0h+var_280]
0x18000610e  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180006114  mov     eax, ebx
0x180006116  mov     rcx, [rbp+1B0h+var_30]
0x18000611d  xor     rcx, rsp; StackCookie
0x180006120  call    __security_check_cookie
0x180006125  lea     r11, [rsp+2B0h+var_20]
0x18000612d  mov     rbx, [r11+38h]
0x180006131  mov     rsi, [r11+40h]
0x180006135  mov     rsp, r11
0x180006138  pop     r15
0x18000613a  pop     r14
0x18000613c  pop     r12
0x18000613e  pop     rdi
0x18000613f  pop     rbp
0x180006140  retn
```
