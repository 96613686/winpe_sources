# CDlpActionWimLayout::WimDetermineImages(void *,int)

- ea: `0x18002eae4`
- end: `0x18002f08f`
- name: `?WimDetermineImages@CDlpActionWimLayout@@AEAAJPEAXH@Z`
- size: `1451`
- prototype: `__int64 __fastcall(CDlpActionWimLayout *__hidden this, void *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, installer_update`

## callers

- `0x180007f78`

## callees

- `0x18000aba4`
- `0x180012f5c`
- `0x18001fd60`
- `0x18002eae4`
- `0x180030740`
- `0x18007ec9a`
- `0x18007ed40`

## import_xrefs

- `WIMGAPI!WIMGetAttributes` at `0x18002eb4b`
- `WIMGAPI!WIMGetAttributes` at `0x18002eb4b`
- `WIMGAPI!WIMGetImageInformation` at `0x18002ebaf`
- `WIMGAPI!WIMGetImageInformation` at `0x18002ebaf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002eb55`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ebb9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002eb55`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ebb9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002f05d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002f05d`
- `UNATTEND!UnattendCtxCleanup` at `0x18002f045`
- `UNATTEND!UnattendCtxCleanup` at `0x18002f045`
- `UNATTEND!UnattendCtxDeserializeBuffer` at `0x18002ec09`
- `UNATTEND!UnattendCtxDeserializeBuffer` at `0x18002ec09`

## string_xrefs

- `0x18002ecab`: `WimDetermineImages: Checking image [%d] for InstallationType: [%s]`
- `0x18002ecff`: `WimDetermineImages: Checking image [%d] for InstallationType: [%s]`
- `0x18002ed4f`: `WimDetermineImages: Checking image [%d] for InstallationType: [%s]`
- `0x18002edfa`: `WimDetermineImages: Checking image [%d] for InstallationType: [%s]`
- `0x18002ecca`: `WIM\IMAGE[*]\WINDOWS\INSTALLATIONTYPE`
- `0x18002ed1e`: `WIM\IMAGE[*]\WINDOWS\INSTALLATIONTYPE`
- `0x18002ed6e`: `WIM\IMAGE[*]\WINDOWS\INSTALLATIONTYPE`
- `0x18002ee19`: `WIM\IMAGE[*]\WINDOWS\INSTALLATIONTYPE`
- `0x18002edc5`: `WimDetermineImages: Install index: [%d], Install count: [%d]`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CDlpActionWimLayout::WimDetermineImages(CDlpActionWimLayout *this, void *a2)
{
  signed int v4; // eax
  signed int v5; // ebx
  __int64 v6; // rcx
  __int64 v7; // rcx
  signed int LastError; // eax
  int v9; // eax
  const unsigned __int16 *v10; // r9
  unsigned int v11; // esi
  unsigned int v12; // ecx
  __int64 v13; // rcx
  int matched; // eax
  const unsigned __int16 *v15; // r9
  __int64 v16; // rcx
  __int64 v17; // rcx
  int v18; // eax
  __int64 v19; // rcx
  int v20; // eax
  int v21; // eax
  __int64 v22; // rcx
  int v23; // eax
  int v24; // eax
  unsigned int v26[2]; // [rsp+20h] [rbp-E0h]
  PCNZWCH lpString1; // [rsp+28h] [rbp-D8h]
  __int64 v28; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v29; // [rsp+38h] [rbp-C8h] BYREF
  HLOCAL hMem[2]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v31[536]; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v32; // [rsp+268h] [rbp+168h]
  int v33; // [rsp+274h] [rbp+174h]

  hMem[0] = 0;
  LODWORD(v28) = 0;
  v29 = 0;
  memset_0(v31, 0, 0x230u);
  if ( (unsigned int)WIMGetAttributes(a2, v31, 560) )
  {
    LODWORD(v28) = 0;
    if ( (unsigned int)WIMGetImageInformation(a2, hMem, &v28) )
    {
      v9 = UnattendCtxDeserializeBuffer(&v29, hMem[0], (unsigned int)v28);
      v5 = v9;
      v7 = *((_QWORD *)this + 11);
      if ( v9 >= 0 )
      {
        *((_QWORD *)this + 95) = 0;
        *((_QWORD *)this + 96) = 0;
        *((_DWORD *)this + 194) = 0;
        if ( v7 )
          CDlpLogT<CEmptyType>::DlpLogFormat(
            v7,
            2,
            L"WimDetermineImages: Checking [%d] images for matching criteria...",
            v32);
        v11 = 1;
        if ( *((_DWORD *)this + 189) )
        {
LABEL_68:
          v12 = v32;
        }
        else
        {
          while ( 1 )
          {
            v12 = v32;
            if ( v11 > v32 )
              break;
            v13 = *((_QWORD *)this + 11);
            if ( v13 )
              CDlpLogT<CEmptyType>::DlpLogFormat(
                v13,
                1,
                L"WimDetermineImages: Checking image [%d] for InstallationType: [%s]",
                v11,
                L"Client");
            matched = CDlpActionWimLayout::WimMatchImageCriteria(
                        this,
                        (struct _UNATTEND_CONTEXT *)&v29,
                        L"WIM\\IMAGE[*]\\WINDOWS\\INSTALLATIONTYPE",
                        v10,
                        v11,
                        L"Client");
            if ( matched == -2147023728 )
            {
              v16 = *((_QWORD *)this + 11);
              if ( v16 )
                CDlpLogT<CEmptyType>::DlpLogFormat(
                  v16,
                  1,
                  L"WimDetermineImages: Checking image [%d] for InstallationType: [%s]",
                  v11,
                  L"Server Core");
              matched = CDlpActionWimLayout::WimMatchImageCriteria(
                          this,
                          (struct _UNATTEND_CONTEXT *)&v29,
                          L"WIM\\IMAGE[*]\\WINDOWS\\INSTALLATIONTYPE",
                          v15,
                          v11,
                          L"Server Core");
              if ( matched == -2147023728 )
              {
                v17 = *((_QWORD *)this + 11);
                if ( v17 )
                  CDlpLogT<CEmptyType>::DlpLogFormat(
                    v17,
                    1,
                    L"WimDetermineImages: Checking image [%d] for InstallationType: [%s]",
                    v11,
                    L"Server");
                matched = CDlpActionWimLayout::WimMatchImageCriteria(
                            this,
                            (struct _UNATTEND_CONTEXT *)&v29,
                            L"WIM\\IMAGE[*]\\WINDOWS\\INSTALLATIONTYPE",
                            v15,
                            v11,
                            L"Server");
              }
            }
            if ( matched < 0 )
            {
              v7 = *((_QWORD *)this + 11);
              if ( matched != -2147023728 )
              {
                v5 = matched;
                if ( !v7 )
                  goto LABEL_86;
                LODWORD(lpString1) = matched;
                v26[0] = 1927;
                goto LABEL_83;
              }
              if ( v7 )
                CDlpLogT<CEmptyType>::DlpLogFormat(
                  v7,
                  1,
                  L"WimDetermineImages: Checking image [%d] for InstallationType: [%s]",
                  v11,
                  L"WindowsPE");
              v20 = CDlpActionWimLayout::WimMatchImageCriteria(
                      this,
                      (struct _UNATTEND_CONTEXT *)&v29,
                      L"WIM\\IMAGE[*]\\WINDOWS\\INSTALLATIONTYPE",
                      v15,
                      v11,
                      L"WindowsPE");
              v7 = *((_QWORD *)this + 11);
              if ( v20 < 0 )
              {
                if ( v20 != -2147023728 )
                {
                  v5 = v20;
                  if ( !v7 )
                    goto LABEL_86;
                  LODWORD(lpString1) = v20;
                  v26[0] = 1957;
                  goto LABEL_83;
                }
                if ( v7 )
                  CDlpLogT<CEmptyType>::DlpLogFormat(
                    v7,
                    1,
                    L"WimDetermineImages: Checking image [%d] for Name: [%s]",
                    v11,
                    L"Windows Setup Media");
                v21 = CDlpActionWimLayout::WimMatchImageCriteria(
                        this,
                        (struct _UNATTEND_CONTEXT *)&v29,
                        L"WIM\\IMAGE[*]\\NAME",
                        v10,
                        v11,
                        L"Windows Setup Media");
                if ( v21 < 0 )
                {
                  v7 = *((_QWORD *)this + 11);
                  if ( v21 == -2147023728 )
                  {
                    v5 = -2147418113;
                    if ( !v7 )
                      goto LABEL_86;
                    LODWORD(lpString1) = -2147418113;
                    v26[0] = 1988;
                  }
                  else
                  {
                    v5 = v21;
                    if ( !v7 )
                      goto LABEL_86;
                    LODWORD(lpString1) = v21;
                    v26[0] = 1983;
                  }
                  goto LABEL_83;
                }
                v10 = (const unsigned __int16 *)*((unsigned int *)this + 192);
                if ( !(_DWORD)v10 )
                {
                  *((_DWORD *)this + 192) = v11;
                  v10 = (const unsigned __int16 *)v11;
                }
                v22 = *((_QWORD *)this + 11);
                if ( v22 )
                  CDlpLogT<CEmptyType>::DlpLogFormat(v22, 2, L"WimDetermineImages: Layout index: [%d]", v10);
              }
              else if ( v11 == v33 )
              {
                *((_DWORD *)this + 194) = v11;
                if ( v7 )
                  CDlpLogT<CEmptyType>::DlpLogFormat(v7, 2, L"WimDetermineImages: Media WinPE index: [%d]", v11);
              }
              else
              {
                *((_DWORD *)this + 193) = v11;
                if ( v7 )
                  CDlpLogT<CEmptyType>::DlpLogFormat(v7, 2, L"WimDetermineImages: WinPE index: [%d]", v11);
              }
            }
            else
            {
              v10 = (const unsigned __int16 *)*((unsigned int *)this + 191);
              if ( (_DWORD)v10 )
              {
                v18 = ++*((_DWORD *)this + 190);
              }
              else
              {
                *((_DWORD *)this + 191) = v11;
                *((_DWORD *)this + 190) = 1;
                v18 = 1;
                v10 = (const unsigned __int16 *)v11;
              }
              v19 = *((_QWORD *)this + 11);
              if ( v19 )
              {
                v26[0] = v18;
                CDlpLogT<CEmptyType>::DlpLogFormat(
                  v19,
                  2,
                  L"WimDetermineImages: Install index: [%d], Install count: [%d]",
                  v10,
                  *(_QWORD *)v26);
              }
            }
            if ( *((_DWORD *)this + 189) )
              goto LABEL_68;
            ++v11;
          }
        }
        v23 = *((_DWORD *)this + 190);
        if ( v12 == 3 )
        {
          if ( v23 && *((_DWORD *)this + 191) && *((_DWORD *)this + 192) && *((_DWORD *)this + 194) )
            goto LABEL_86;
          v5 = -2147023728;
          v7 = *((_QWORD *)this + 11);
          if ( !v7 )
            goto LABEL_86;
          LODWORD(lpString1) = -2147023728;
          v26[0] = 2000;
        }
        else
        {
          if ( v23
            && *((_DWORD *)this + 191)
            && *((_DWORD *)this + 192)
            && *((_DWORD *)this + 193)
            && *((_DWORD *)this + 194) )
          {
            goto LABEL_86;
          }
          v5 = -2147023728;
          v7 = *((_QWORD *)this + 11);
          if ( !v7 )
            goto LABEL_86;
          LODWORD(lpString1) = -2147023728;
          v26[0] = 2008;
        }
      }
      else
      {
        if ( !v7 )
          goto LABEL_86;
        LODWORD(lpString1) = v9;
        v26[0] = 1868;
      }
      goto LABEL_83;
    }
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError )
    {
      if ( LastError > 0 )
        v5 = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      v5 = -2147467259;
    }
    if ( *((_QWORD *)this + 11) )
    {
      v6 = 0;
      if ( v5 < 0 )
      {
        LODWORD(lpString1) = v5;
        v26[0] = 1864;
        goto LABEL_9;
      }
LABEL_85:
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v6);
    }
  }
  else
  {
    v4 = GetLastError();
    v5 = v4;
    if ( v4 )
    {
      if ( v4 > 0 )
        v5 = (unsigned __int16)v4 | 0x80070000;
    }
    else
    {
      v5 = -2147467259;
    }
    if ( *((_QWORD *)this + 11) )
    {
      v6 = 0;
      if ( v5 < 0 )
      {
        LODWORD(lpString1) = v5;
        v26[0] = 1859;
LABEL_9:
        v7 = *((_QWORD *)this + 11);
LABEL_83:
        v24 = CDlpLogT<CEmptyType>::DlpLogFormat(
                v7,
                4,
                L"%s(%d): Result = 0x%X",
                L"CDlpActionWimLayout::WimDetermineImages",
                *(_QWORD *)v26,
                lpString1,
                v28,
                v29);
        v6 = (unsigned int)v24;
        if ( v24 < 0 )
          CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v24);
        goto LABEL_85;
      }
      goto LABEL_85;
    }
  }
LABEL_86:
  UnattendCtxCleanup(&v29);
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v5);
  if ( hMem[0] )
    LocalFree(hMem[0]);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18002eae4  mov     [rsp-8+arg_10], rbx
0x18002eae9  push    rbp
0x18002eaea  push    rsi
0x18002eaeb  push    rdi
0x18002eaec  push    r12
0x18002eaee  push    r13
0x18002eaf0  push    r14
0x18002eaf2  push    r15
0x18002eaf4  lea     rbp, [rsp-190h]
0x18002eafc  sub     rsp, 290h
0x18002eb03  mov     rax, cs:__security_cookie
0x18002eb0a  xor     rax, rsp
0x18002eb0d  mov     [rbp+1C0h+var_40], rax
0x18002eb14  mov     rbx, rdx
0x18002eb17  mov     rdi, rcx
0x18002eb1a  xor     r14d, r14d
0x18002eb1d  mov     [rsp+2C0h+hMem], r14
0x18002eb22  mov     dword ptr [rsp+2C0h+var_290], r14d
0x18002eb27  mov     [rsp+2C0h+var_288], r14
0x18002eb2c  mov     esi, 230h
0x18002eb31  mov     r8d, esi; Size
0x18002eb34  xor     edx, edx; Val
0x18002eb36  lea     rcx, [rsp+2C0h+var_270]; void *
0x18002eb3b  call    memset_0
0x18002eb40  mov     r8d, esi
0x18002eb43  lea     rdx, [rsp+2C0h+var_270]
0x18002eb48  mov     rcx, rbx
0x18002eb4b  call    cs:__imp_WIMGetAttributes
0x18002eb51  test    eax, eax
0x18002eb53  jnz     short loc_18002EB9D
0x18002eb55  call    cs:__imp_GetLastError
0x18002eb5b  mov     ebx, eax
0x18002eb5d  test    eax, eax
0x18002eb5f  jnz     short loc_18002EB68
0x18002eb61  mov     ebx, 80004005h
0x18002eb66  jmp     short loc_18002EB73
0x18002eb68  jle     short loc_18002EB73
0x18002eb6a  movzx   ebx, ax
0x18002eb6d  or      ebx, 80070000h
0x18002eb73  cmp     [rdi+58h], r14
0x18002eb77  jz      loc_18002F040
0x18002eb7d  mov     ecx, r14d
0x18002eb80  test    ebx, ebx
0x18002eb82  jns     loc_18002F03B
0x18002eb88  mov     dword ptr [rsp+2C0h+lpString1], ebx
0x18002eb8c  mov     [rsp+2C0h+var_2A0], 743h
0x18002eb94  mov     rcx, [rdi+58h]
0x18002eb98  jmp     loc_18002F018
0x18002eb9d  mov     dword ptr [rsp+2C0h+var_290], r14d
0x18002eba2  lea     r8, [rsp+2C0h+var_290]
0x18002eba7  lea     rdx, [rsp+2C0h+hMem]
0x18002ebac  mov     rcx, rbx
0x18002ebaf  call    cs:__imp_WIMGetImageInformation
0x18002ebb5  test    eax, eax
0x18002ebb7  jnz     short loc_18002EBFA
0x18002ebb9  call    cs:__imp_GetLastError
0x18002ebbf  mov     ebx, eax
0x18002ebc1  test    eax, eax
0x18002ebc3  jnz     short loc_18002EBCC
0x18002ebc5  mov     ebx, 80004005h
0x18002ebca  jmp     short loc_18002EBD7
0x18002ebcc  jle     short loc_18002EBD7
0x18002ebce  movzx   ebx, ax
0x18002ebd1  or      ebx, 80070000h
0x18002ebd7  cmp     [rdi+58h], r14
0x18002ebdb  jz      loc_18002F040
0x18002ebe1  mov     ecx, r14d
0x18002ebe4  test    ebx, ebx
0x18002ebe6  jns     loc_18002F03B
0x18002ebec  mov     dword ptr [rsp+2C0h+lpString1], ebx
0x18002ebf0  mov     [rsp+2C0h+var_2A0], 748h
0x18002ebf8  jmp     short loc_18002EB94
0x18002ebfa  mov     r8d, dword ptr [rsp+2C0h+var_290]
0x18002ebff  mov     rdx, [rsp+2C0h+hMem]
0x18002ec04  lea     rcx, [rsp+2C0h+var_288]
0x18002ec09  call    cs:__imp_UnattendCtxDeserializeBuffer
0x18002ec0f  mov     ebx, eax
0x18002ec11  mov     rcx, [rdi+58h]
0x18002ec15  test    eax, eax
0x18002ec17  jns     short loc_18002EC33
0x18002ec19  test    rcx, rcx
0x18002ec1c  jz      loc_18002F040
0x18002ec22  mov     dword ptr [rsp+2C0h+lpString1], eax
0x18002ec26  mov     [rsp+2C0h+var_2A0], 74Ch
0x18002ec2e  jmp     loc_18002F018
0x18002ec33  mov     [rdi+2F8h], r14
0x18002ec3a  mov     [rdi+300h], r14
0x18002ec41  mov     [rdi+308h], r14d
0x18002ec48  mov     r13d, 2
0x18002ec4e  test    rcx, rcx
0x18002ec51  jz      short loc_18002EC69
0x18002ec53  mov     r9d, [rbp+1C0h+var_58]
0x18002ec5a  lea     r8, aWimdetermineim_4; "WimDetermineImages: Checking [%d] image"...
0x18002ec61  mov     edx, r13d
0x18002ec64  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x18002ec69  mov     r12d, 1
0x18002ec6f  mov     esi, r12d
0x18002ec72  mov     r15d, 80070490h
0x18002ec78  cmp     [rdi+2F4h], r14d
0x18002ec7f  jnz     loc_18002EF88
0x18002ec85  lea     rax, aClient; "Client"
0x18002ec8c  mov     ecx, [rbp+1C0h+var_58]
0x18002ec92  cmp     esi, ecx
0x18002ec94  ja      loc_18002EF8E
0x18002ec9a  mov     rcx, [rdi+58h]
0x18002ec9e  test    rcx, rcx
0x18002eca1  jz      short loc_18002ECC1
0x18002eca3  mov     qword ptr [rsp+2C0h+var_2A0], rax
0x18002eca8  mov     r9d, esi
0x18002ecab  lea     r8, aWimdetermineim_5; "WimDetermineImages: Checking image [%d]"...
0x18002ecb2  mov     edx, r12d
0x18002ecb5  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x18002ecba  lea     rax, aClient; "Client"
0x18002ecc1  mov     [rsp+2C0h+lpString1], rax; lpString1
0x18002ecc6  mov     [rsp+2C0h+var_2A0], esi; unsigned int
0x18002ecca  lea     r8, aWimImageWindow; "WIM\\IMAGE[*]\\WINDOWS\\INSTALLATIONTYP"...
0x18002ecd1  lea     rdx, [rsp+2C0h+var_288]; struct _UNATTEND_CONTEXT *
0x18002ecd6  mov     rcx, rdi; this
0x18002ecd9  call    ?WimMatchImageCriteria@CDlpActionWimLayout@@AEAAJPEAU_UNATTEND_CONTEXT@@PEBG1K1@Z; CDlpActionWimLayout::WimMatchImageCriteria(_UNATTEND_CONTEXT *,ushort const *,ushort const *,ulong,ushort const *)
0x18002ecde  cmp     eax, r15d
0x18002ece1  jnz     loc_18002ED82
0x18002ece7  mov     rcx, [rdi+58h]
0x18002eceb  test    rcx, rcx
0x18002ecee  jz      short loc_18002ED0E
0x18002ecf0  lea     rax, aServerCore; "Server Core"
0x18002ecf7  mov     qword ptr [rsp+2C0h+var_2A0], rax
0x18002ecfc  mov     r9d, esi
0x18002ecff  lea     r8, aWimdetermineim_5; "WimDetermineImages: Checking image [%d]"...
0x18002ed06  mov     edx, r12d
0x18002ed09  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x18002ed0e  lea     rax, aServerCore; "Server Core"
0x18002ed15  mov     [rsp+2C0h+lpString1], rax; lpString1
0x18002ed1a  mov     [rsp+2C0h+var_2A0], esi; unsigned int
0x18002ed1e  lea     r8, aWimImageWindow; "WIM\\IMAGE[*]\\WINDOWS\\INSTALLATIONTYP"...
0x18002ed25  lea     rdx, [rsp+2C0h+var_288]; struct _UNATTEND_CONTEXT *
0x18002ed2a  mov     rcx, rdi; this
0x18002ed2d  call    ?WimMatchImageCriteria@CDlpActionWimLayout@@AEAAJPEAU_UNATTEND_CONTEXT@@PEBG1K1@Z; CDlpActionWimLayout::WimMatchImageCriteria(_UNATTEND_CONTEXT *,ushort const *,ushort const *,ulong,ushort const *)
0x18002ed32  cmp     eax, r15d
0x18002ed35  jnz     short loc_18002ED82
0x18002ed37  mov     rcx, [rdi+58h]
0x18002ed3b  test    rcx, rcx
0x18002ed3e  jz      short loc_18002ED5E
0x18002ed40  lea     rax, aServer; "Server"
0x18002ed47  mov     qword ptr [rsp+2C0h+var_2A0], rax
0x18002ed4c  mov     r9d, esi
0x18002ed4f  lea     r8, aWimdetermineim_5; "WimDetermineImages: Checking image [%d]"...
0x18002ed56  mov     edx, r12d
0x18002ed59  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x18002ed5e  lea     rax, aServer; "Server"
0x18002ed65  mov     [rsp+2C0h+lpString1], rax; lpString1
0x18002ed6a  mov     [rsp+2C0h+var_2A0], esi; unsigned int
0x18002ed6e  lea     r8, aWimImageWindow; "WIM\\IMAGE[*]\\WINDOWS\\INSTALLATIONTYP"...
0x18002ed75  lea     rdx, [rsp+2C0h+var_288]; struct _UNATTEND_CONTEXT *
0x18002ed7a  mov     rcx, rdi; this
0x18002ed7d  call    ?WimMatchImageCriteria@CDlpActionWimLayout@@AEAAJPEAU_UNATTEND_CONTEXT@@PEBG1K1@Z; CDlpActionWimLayout::WimMatchImageCriteria(_UNATTEND_CONTEXT *,ushort const *,ushort const *,ulong,ushort const *)
0x18002ed82  test    eax, eax
0x18002ed84  js      short loc_18002EDD9
0x18002ed86  mov     r9d, [rdi+2FCh]
0x18002ed8d  test    r9d, r9d
0x18002ed90  jnz     short loc_18002EDA7
0x18002ed92  mov     [rdi+2FCh], esi
0x18002ed98  mov     [rdi+2F8h], r12d
0x18002ed9f  mov     eax, r12d
0x18002eda2  mov     r9d, esi
0x18002eda5  jmp     short loc_18002EDB4
0x18002eda7  add     [rdi+2F8h], r12d
0x18002edae  mov     eax, [rdi+2F8h]
0x18002edb4  mov     rcx, [rdi+58h]
0x18002edb8  test    rcx, rcx
0x18002edbb  jz      loc_18002EEF7
0x18002edc1  mov     [rsp+2C0h+var_2A0], eax
0x18002edc5  lea     r8, aWimdetermineim_2; "WimDetermineImages: Install index: [%d]"...
0x18002edcc  mov     edx, r13d
0x18002edcf  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x18002edd4  jmp     loc_18002EEF7
0x18002edd9  mov     rcx, [rdi+58h]
0x18002eddd  cmp     eax, r15d
0x18002ede0  jnz     loc_18002EF6C
0x18002ede6  test    rcx, rcx
0x18002ede9  jz      short loc_18002EE09
0x18002edeb  lea     rax, aWindowspe; "WindowsPE"
0x18002edf2  mov     qword ptr [rsp+2C0h+var_2A0], rax
0x18002edf7  mov     r9d, esi
0x18002edfa  lea     r8, aWimdetermineim_5; "WimDetermineImages: Checking image [%d]"...
0x18002ee01  mov     edx, r12d
0x18002ee04  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x18002ee09  lea     rax, aWindowspe; "WindowsPE"
0x18002ee10  mov     [rsp+2C0h+lpString1], rax; lpString1
0x18002ee15  mov     [rsp+2C0h+var_2A0], esi; unsigned int
0x18002ee19  lea     r8, aWimImageWindow; "WIM\\IMAGE[*]\\WINDOWS\\INSTALLATIONTYP"...
0x18002ee20  lea     rdx, [rsp+2C0h+var_288]; struct _UNATTEND_CONTEXT *
0x18002ee25  mov     rcx, rdi; this
0x18002ee28  call    ?WimMatchImageCriteria@CDlpActionWimLayout@@AEAAJPEAU_UNATTEND_CONTEXT@@PEBG1K1@Z; CDlpActionWimLayout::WimMatchImageCriteria(_UNATTEND_CONTEXT *,ushort const *,ushort const *,ulong,ushort const *)
0x18002ee2d  mov     rcx, [rdi+58h]
0x18002ee31  test    eax, eax
0x18002ee33  js      short loc_18002EE76
0x18002ee35  cmp     esi, [rbp+1C0h+var_4C]
0x18002ee3b  jnz     short loc_18002EE5B
0x18002ee3d  mov     [rdi+308h], esi
0x18002ee43  test    rcx, rcx
0x18002ee46  jz      loc_18002EEF7
0x18002ee4c  mov     r9d, esi
0x18002ee4f  lea     r8, aWimdetermineim_1; "WimDetermineImages: Media WinPE index: "...
0x18002ee56  jmp     loc_18002EEEF
0x18002ee5b  mov     [rdi+304h], esi
0x18002ee61  test    rcx, rcx
0x18002ee64  jz      loc_18002EEF7
0x18002ee6a  mov     r9d, esi
0x18002ee6d  lea     r8, aWimdetermineim; "WimDetermineImages: WinPE index: [%d]"
0x18002ee74  jmp     short loc_18002EEEF
0x18002ee76  cmp     eax, r15d
0x18002ee79  jnz     loc_18002EF50
0x18002ee7f  test    rcx, rcx
0x18002ee82  jz      short loc_18002EEA2
0x18002ee84  lea     rax, aWindowsSetupMe; "Windows Setup Media"
0x18002ee8b  mov     qword ptr [rsp+2C0h+var_2A0], rax
0x18002ee90  mov     r9d, esi
0x18002ee93  lea     r8, aWimdetermineim_3; "WimDetermineImages: Checking image [%d]"...
0x18002ee9a  mov     edx, r12d
0x18002ee9d  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x18002eea2  lea     rax, aWindowsSetupMe; "Windows Setup Media"
0x18002eea9  mov     [rsp+2C0h+lpString1], rax; lpString1
0x18002eeae  mov     [rsp+2C0h+var_2A0], esi; unsigned int
0x18002eeb2  lea     r8, aWimImageName; "WIM\\IMAGE[*]\\NAME"
0x18002eeb9  lea     rdx, [rsp+2C0h+var_288]; struct _UNATTEND_CONTEXT *
0x18002eebe  mov     rcx, rdi; this
0x18002eec1  call    ?WimMatchImageCriteria@CDlpActionWimLayout@@AEAAJPEAU_UNATTEND_CONTEXT@@PEBG1K1@Z; CDlpActionWimLayout::WimMatchImageCriteria(_UNATTEND_CONTEXT *,ushort const *,ushort const *,ulong,ushort const *)
0x18002eec6  test    eax, eax
0x18002eec8  js      short loc_18002EF0C
0x18002eeca  mov     r9d, [rdi+300h]
0x18002eed1  test    r9d, r9d
0x18002eed4  jnz     short loc_18002EEDF
0x18002eed6  mov     [rdi+300h], esi
0x18002eedc  mov     r9d, esi
0x18002eedf  mov     rcx, [rdi+58h]
0x18002eee3  test    rcx, rcx
0x18002eee6  jz      short loc_18002EEF7
0x18002eee8  lea     r8, aWimdetermineim_0; "WimDetermineImages: Layout index: [%d]"
0x18002eeef  mov     edx, r13d
0x18002eef2  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x18002eef7  cmp     [rdi+2F4h], r14d
0x18002eefe  jnz     loc_18002EF88
0x18002ef04  add     esi, r12d
0x18002ef07  jmp     loc_18002EC85
0x18002ef0c  mov     rcx, [rdi+58h]
0x18002ef10  cmp     eax, r15d
0x18002ef13  jz      short loc_18002EF31
0x18002ef15  mov     ebx, eax
0x18002ef17  test    rcx, rcx
0x18002ef1a  jz      loc_18002F040
0x18002ef20  mov     dword ptr [rsp+2C0h+lpString1], eax
0x18002ef24  mov     [rsp+2C0h+var_2A0], 7BFh
0x18002ef2c  jmp     loc_18002F018
0x18002ef31  mov     ebx, 8000FFFFh
0x18002ef36  test    rcx, rcx
0x18002ef39  jz      loc_18002F040
0x18002ef3f  mov     dword ptr [rsp+2C0h+lpString1], ebx
0x18002ef43  mov     [rsp+2C0h+var_2A0], 7C4h
0x18002ef4b  jmp     loc_18002F018
0x18002ef50  mov     ebx, eax
0x18002ef52  test    rcx, rcx
0x18002ef55  jz      loc_18002F040
0x18002ef5b  mov     dword ptr [rsp+2C0h+lpString1], eax
0x18002ef5f  mov     [rsp+2C0h+var_2A0], 7A5h
0x18002ef67  jmp     loc_18002F018
0x18002ef6c  mov     ebx, eax
0x18002ef6e  test    rcx, rcx
0x18002ef71  jz      loc_18002F040
0x18002ef77  mov     dword ptr [rsp+2C0h+lpString1], eax
0x18002ef7b  mov     [rsp+2C0h+var_2A0], 787h
0x18002ef83  jmp     loc_18002F018
0x18002ef88  mov     ecx, [rbp+1C0h+var_58]
0x18002ef8e  mov     eax, [rdi+2F8h]
0x18002ef94  cmp     ecx, 3
0x18002ef97  jnz     short loc_18002EFD7
0x18002ef99  test    eax, eax
0x18002ef9b  jz      short loc_18002EFBC
0x18002ef9d  cmp     [rdi+2FCh], r14d
0x18002efa4  jz      short loc_18002EFBC
0x18002efa6  cmp     [rdi+300h], r14d
0x18002efad  jz      short loc_18002EFBC
0x18002efaf  cmp     [rdi+308h], r14d
0x18002efb6  jnz     loc_18002F040
0x18002efbc  mov     ebx, r15d
0x18002efbf  mov     rcx, [rdi+58h]
0x18002efc3  test    rcx, rcx
0x18002efc6  jz      short loc_18002F040
0x18002efc8  mov     dword ptr [rsp+2C0h+lpString1], r15d
0x18002efcd  mov     [rsp+2C0h+var_2A0], 7D0h
0x18002efd5  jmp     short loc_18002F018
0x18002efd7  test    eax, eax
0x18002efd9  jz      short loc_18002EFFF
0x18002efdb  cmp     [rdi+2FCh], r14d
0x18002efe2  jz      short loc_18002EFFF
0x18002efe4  cmp     [rdi+300h], r14d
0x18002efeb  jz      short loc_18002EFFF
0x18002efed  cmp     [rdi+304h], r14d
0x18002eff4  jz      short loc_18002EFFF
0x18002eff6  cmp     [rdi+308h], r14d
0x18002effd  jnz     short loc_18002F040
  ... truncated ...
```
