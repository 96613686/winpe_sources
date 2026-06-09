# _lambda_3fc51519e205e21089bea3bbc6cbbfea_::operator()

- ea: `0x14009ace0`
- end: `0x14009b165`
- name: `_lambda_3fc51519e205e21089bea3bbc6cbbfea_::operator()`
- size: `1157`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops`

## callers

- `0x14009c1b0`

## callees

- `0x140005530`
- `0x140005554`
- `0x140006314`
- `0x140006338`
- `0x140007938`
- `0x140009858`
- `0x14000ccac`
- `0x14001f6b4`
- `0x140035800`
- `0x140047e78`
- `0x1400601dc`
- `0x1400608a0`
- `0x140060f58`
- `0x1400930a4`
- `0x14009380c`
- `0x14009ace0`
- `0x14009b4ac`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14009ae62`
- `KERNEL32!GetLastError` at `0x14009afe0`
- `KERNEL32!GetLastError` at `0x14009b045`
- `KERNEL32!GetLastError` at `0x14009b0a9`
- `KERNEL32!GetLastError` at `0x14009ae62`
- `KERNEL32!GetLastError` at `0x14009afe0`
- `KERNEL32!GetLastError` at `0x14009b045`
- `KERNEL32!GetLastError` at `0x14009b0a9`
- `WINHTTP!WinHttpQueryHeaders` at `0x14009ad3e`
- `WINHTTP!WinHttpQueryHeaders` at `0x14009ae54`
- `WINHTTP!WinHttpQueryHeaders` at `0x14009aece`
- `WINHTTP!WinHttpQueryHeaders` at `0x14009ad3e`
- `WINHTTP!WinHttpQueryHeaders` at `0x14009ae54`
- `WINHTTP!WinHttpQueryHeaders` at `0x14009aece`
- `WINHTTP!WinHttpReadData` at `0x14009ad8b`
- `WINHTTP!WinHttpReadData` at `0x14009ad8b`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall lambda_3fc51519e205e21089bea3bbc6cbbfea_::operator()(__int64 a1, void *a2)
{
  __int64 v4; // rdx
  DWORD v5; // ecx
  char *v6; // r14
  char *v7; // rbx
  char v8; // r9
  unsigned __int64 v9; // rcx
  __int128 *p_Src; // rax
  __int128 *v11; // r8
  signed int v12; // eax
  unsigned int v13; // ebx
  unsigned __int64 v14; // r14
  unsigned __int64 v15; // rbx
  void *v16; // r13
  _QWORD *v17; // r12
  _QWORD *v18; // rsi
  _QWORD *v19; // r14
  char *v20; // r15
  char **v21; // rdi
  __int64 v22; // rcx
  __int64 v23; // rcx
  unsigned __int64 v24; // rdx
  signed int v25; // eax
  unsigned int v26; // ebx
  signed int v27; // eax
  unsigned int v28; // ebx
  signed int LastError; // eax
  unsigned int v30; // ebx
  DWORD dwNumberOfBytesRead; // [rsp+30h] [rbp-D0h] BYREF
  DWORD lpdwBufferLength; // [rsp+34h] [rbp-CCh] BYREF
  DWORD dwBufferLength; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE pExceptionObject[40]; // [rsp+40h] [rbp-C0h] BYREF
  void *v35; // [rsp+68h] [rbp-98h]
  _BYTE v36[16]; // [rsp+70h] [rbp-90h] BYREF
  __int128 Src; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int64 v38; // [rsp+90h] [rbp-70h]
  unsigned __int64 v39; // [rsp+98h] [rbp-68h]
  __int128 v40; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v41; // [rsp+B0h] [rbp-50h]
  __int64 v42; // [rsp+B8h] [rbp-48h]
  _BYTE Buffer[2048]; // [rsp+D0h] [rbp-30h] BYREF

  dwBufferLength = 4;
  if ( !WinHttpQueryHeaders(a2, 0x20000013u, 0, *(LPVOID *)a1, &dwBufferLength, 0) )
  {
    LastError = GetLastError();
    v30 = LastError;
    if ( LastError > 0 )
      v30 = (unsigned __int16)LastError | 0x80070000;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 17, WPP_b4f7f3e5d1fd340cfdb1f1c040853efe_Traceguids, v30);
    ErrorCodeException::ErrorCodeException((ErrorCodeException *)&v40, v30);
    throw (ErrorCodeException *)&v40;
  }
  dwNumberOfBytesRead = 0;
  memset_0(Buffer, 0, sizeof(Buffer));
  Src = 0;
  v38 = 0;
  v39 = 15;
  LOBYTE(Src) = 0;
  do
  {
    if ( !WinHttpReadData(a2, Buffer, 0x800u, &dwNumberOfBytesRead) )
    {
      v27 = GetLastError();
      v28 = v27;
      if ( v27 > 0 )
        v28 = (unsigned __int16)v27 | 0x80070000;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 18, WPP_b4f7f3e5d1fd340cfdb1f1c040853efe_Traceguids, v28);
      ErrorCodeException::ErrorCodeException((ErrorCodeException *)pExceptionObject, v28);
      throw (ErrorCodeException *)pExceptionObject;
    }
    v5 = dwNumberOfBytesRead;
    v6 = &Buffer[dwNumberOfBytesRead];
    v7 = Buffer;
    if ( Buffer != v6 )
    {
      do
      {
        v8 = *v7;
        v9 = v38;
        if ( v38 >= v39 )
        {
          std::string::_Reallocate_grow_by<_lambda_319d5e083f45f90dcdce5dce53cbb275_,char>(&Src);
        }
        else
        {
          ++v38;
          p_Src = &Src;
          if ( v39 > 0xF )
            p_Src = (__int128 *)Src;
          *((_BYTE *)p_Src + v9) = v8;
          *((_BYTE *)p_Src + v9 + 1) = 0;
        }
        ++v7;
      }
      while ( v7 != v6 );
      v5 = dwNumberOfBytesRead;
    }
  }
  while ( v5 == 2048 );
  v11 = &Src;
  if ( v39 > 0xF )
    v11 = (__int128 *)Src;
  StringAlgo::ToUnicode(&v40, v4, v11);
  std::wstring::operator=(*(_QWORD *)a1 + 8LL, &v40);
  std::wstring::~wstring((char **)&v40);
  if ( *(_BYTE *)(a1 + 8) )
  {
    lpdwBufferLength = 0;
    if ( !WinHttpQueryHeaders(a2, 0x16u, 0, 0, &lpdwBufferLength, 0) )
    {
      v12 = GetLastError();
      v13 = v12;
      if ( v12 != 122 && v12 )
      {
        if ( v12 > 0 )
          v13 = (unsigned __int16)v12 | 0x80070000;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
          WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 19, WPP_b4f7f3e5d1fd340cfdb1f1c040853efe_Traceguids, v13);
        ErrorCodeException::ErrorCodeException((ErrorCodeException *)pExceptionObject, v13);
        throw (ErrorCodeException *)pExceptionObject;
      }
      v14 = (unsigned __int64)lpdwBufferLength >> 1;
      v15 = saturated_mul(v14, 2u);
      v16 = operator new[](v15);
      memset_0(v16, 0, v15);
      v35 = v16;
      if ( !WinHttpQueryHeaders(a2, 0x15u, 0, v16, &lpdwBufferLength, 0) )
      {
        v25 = GetLastError();
        v26 = v25;
        if ( v25 > 0 )
          v26 = (unsigned __int16)v25 | 0x80070000;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
          WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 20, WPP_b4f7f3e5d1fd340cfdb1f1c040853efe_Traceguids, v26);
        ErrorCodeException::ErrorCodeException((ErrorCodeException *)pExceptionObject, v26);
        throw (ErrorCodeException *)pExceptionObject;
      }
      v40 = 0;
      v41 = 0;
      v42 = 0;
      std::wstring::_Construct<1,unsigned short const *>((char **)&v40, v16, v14);
      v17 = (_QWORD *)ParseHeaders(v36, &v40);
      v18 = (_QWORD *)(*(_QWORD *)a1 + 40LL);
      if ( v18 != v17 )
      {
        v19 = (_QWORD *)*v18;
        v20 = *(char **)(*v18 + 8LL);
        while ( !v20[25] )
        {
          std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>>>(
            v18,
            v18,
            *((_QWORD *)v20 + 2));
          v21 = (char **)v20;
          v20 = *(char **)v20;
          std::wstring::~wstring(v21 + 8);
          std::wstring::~wstring(v21 + 4);
          operator delete(v21, 0x60u);
        }
        v19[1] = v19;
        *v19 = v19;
        v19[2] = v19;
        v18[1] = 0;
        v22 = *v18;
        *v18 = *v17;
        *v17 = v22;
        v23 = v18[1];
        v18[1] = v17[1];
        v17[1] = v23;
      }
      std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(v36);
      std::wstring::~wstring((char **)&v40);
      operator delete(v16, v24);
    }
  }
  std::string::~string((char **)&Src);
}

```

## disassembly

```asm
0x14009ace0  mov     [rsp-8+arg_10], rbx
0x14009ace5  push    rbp
0x14009ace6  push    rsi
0x14009ace7  push    rdi
0x14009ace8  push    r12
0x14009acea  push    r13
0x14009acec  push    r14
0x14009acee  push    r15
0x14009acf0  lea     rbp, [rsp-7E0h]
0x14009acf8  sub     rsp, 8E0h
0x14009acff  mov     rax, cs:__security_cookie
0x14009ad06  xor     rax, rsp
0x14009ad09  mov     [rbp+810h+var_40], rax
0x14009ad10  mov     rdi, rdx
0x14009ad13  mov     rsi, rcx
0x14009ad16  xor     r15d, r15d
0x14009ad19  mov     [rsp+910h+dwBufferLength], 4
0x14009ad21  mov     [rsp+910h+lpdwIndex], r15; lpdwIndex
0x14009ad26  lea     rax, [rsp+910h+dwBufferLength]
0x14009ad2b  mov     [rsp+910h+lpdwBufferLength], rax; lpdwBufferLength
0x14009ad30  mov     r9, [rcx]; lpBuffer
0x14009ad33  xor     r8d, r8d; pwszName
0x14009ad36  mov     edx, 20000013h; dwInfoLevel
0x14009ad3b  mov     rcx, rdi; hRequest
0x14009ad3e  call    cs:__imp_WinHttpQueryHeaders
0x14009ad44  test    eax, eax
0x14009ad46  jz      loc_14009B0A9
0x14009ad4c  mov     [rsp+910h+dwNumberOfBytesRead], r15d
0x14009ad51  mov     r12d, 800h
0x14009ad57  mov     r8d, r12d; Size
0x14009ad5a  xor     edx, edx; Val
0x14009ad5c  lea     rcx, [rbp+810h+Buffer]; void *
0x14009ad60  call    memset_0
0x14009ad65  xorps   xmm0, xmm0
0x14009ad68  movups  [rbp+810h+Src], xmm0
0x14009ad6c  mov     [rbp+810h+var_880], r15
0x14009ad70  mov     [rbp+810h+var_878], 0Fh
0x14009ad78  mov     byte ptr [rbp+810h+Src], r15b
0x14009ad7c  lea     r9, [rsp+910h+dwNumberOfBytesRead]; lpdwNumberOfBytesRead
0x14009ad81  mov     r8d, r12d; dwNumberOfBytesToRead
0x14009ad84  lea     rdx, [rbp+810h+Buffer]; lpBuffer
0x14009ad88  mov     rcx, rdi; hRequest
0x14009ad8b  call    cs:__imp_WinHttpReadData
0x14009ad91  test    eax, eax
0x14009ad93  jz      loc_14009B045
0x14009ad99  mov     ecx, [rsp+910h+dwNumberOfBytesRead]
0x14009ad9d  lea     r14, [rbp+810h+Buffer]
0x14009ada1  add     r14, rcx
0x14009ada4  lea     rbx, [rbp+810h+Buffer]
0x14009ada8  lea     rax, [rbp+810h+Buffer]
0x14009adac  cmp     rax, r14
0x14009adaf  jz      short loc_14009ADF4
0x14009adb1  mov     r9b, [rbx]
0x14009adb4  mov     rcx, [rbp+810h+var_880]
0x14009adb8  cmp     rcx, [rbp+810h+var_878]
0x14009adbc  jnb     short loc_14009ADDF
0x14009adbe  lea     rax, [rcx+1]
0x14009adc2  mov     [rbp+810h+var_880], rax
0x14009adc6  lea     rax, [rbp+810h+Src]
0x14009adca  cmp     [rbp+810h+var_878], 0Fh
0x14009adcf  cmova   rax, qword ptr [rbp+810h+Src]
0x14009add4  mov     [rax+rcx], r9b
0x14009add8  mov     [rax+rcx+1], r15b
0x14009addd  jmp     short loc_14009ADE8
0x14009addf  lea     rcx, [rbp+810h+Src]; Src
0x14009ade3  call    ??$_Reallocate_grow_by@V_lambda_319d5e083f45f90dcdce5dce53cbb275_@@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_319d5e083f45f90dcdce5dce53cbb275_@@D@Z; std::string::_Reallocate_grow_by<_lambda_319d5e083f45f90dcdce5dce53cbb275_,char>(unsigned __int64,_lambda_319d5e083f45f90dcdce5dce53cbb275_,char)
0x14009ade8  inc     rbx
0x14009adeb  cmp     rbx, r14
0x14009adee  jnz     short loc_14009ADB1
0x14009adf0  mov     ecx, [rsp+910h+dwNumberOfBytesRead]
0x14009adf4  cmp     ecx, r12d
0x14009adf7  jz      short loc_14009AD7C
0x14009adf9  lea     r8, [rbp+810h+Src]
0x14009adfd  cmp     [rbp+810h+var_878], 0Fh
0x14009ae02  cmova   r8, qword ptr [rbp+810h+Src]
0x14009ae07  lea     rcx, [rbp+810h+var_870]
0x14009ae0b  call    ?ToUnicode@StringAlgo@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@HPEBDH@Z; StringAlgo::ToUnicode(int,char const *,int)
0x14009ae10  mov     rcx, [rsi]
0x14009ae13  add     rcx, 8
0x14009ae17  lea     rdx, [rbp+810h+var_870]
0x14009ae1b  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x14009ae20  lea     rcx, [rbp+810h+var_870]
0x14009ae24  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14009ae29  cmp     [rsi+8], r15b
0x14009ae2d  jz      loc_14009AFAD
0x14009ae33  mov     [rsp+910h+var_8DC], r15d
0x14009ae38  mov     [rsp+910h+lpdwIndex], r15; lpdwIndex
0x14009ae3d  lea     rax, [rsp+910h+var_8DC]
0x14009ae42  mov     [rsp+910h+lpdwBufferLength], rax; lpdwBufferLength
0x14009ae47  xor     r9d, r9d; lpBuffer
0x14009ae4a  xor     r8d, r8d; pwszName
0x14009ae4d  lea     edx, [r9+16h]; dwInfoLevel
0x14009ae51  mov     rcx, rdi; hRequest
0x14009ae54  call    cs:__imp_WinHttpQueryHeaders
0x14009ae5a  test    eax, eax
0x14009ae5c  jnz     loc_14009AFAD
0x14009ae62  call    cs:__imp_GetLastError
0x14009ae68  mov     ebx, eax
0x14009ae6a  cmp     eax, 7Ah ; 'z'
0x14009ae6d  jz      short loc_14009AE77
0x14009ae6f  test    eax, eax
0x14009ae71  jnz     loc_14009B10B
0x14009ae77  mov     r14d, [rsp+910h+var_8DC]
0x14009ae7c  shr     r14, 1
0x14009ae7f  mov     eax, 2
0x14009ae84  mul     r14
0x14009ae87  mov     rbx, rax
0x14009ae8a  mov     rax, 0FFFFFFFFFFFFFFFFh
0x14009ae91  cmovb   rbx, rax
0x14009ae95  mov     rcx, rbx; unsigned __int64
0x14009ae98  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x14009ae9d  mov     r13, rax
0x14009aea0  mov     r8, rbx; Size
0x14009aea3  xor     edx, edx; Val
0x14009aea5  mov     rcx, rax; void *
0x14009aea8  call    memset_0
0x14009aead  mov     [rsp+910h+var_8A8], r13
0x14009aeb2  mov     [rsp+910h+lpdwIndex], r15; lpdwIndex
0x14009aeb7  lea     rax, [rsp+910h+var_8DC]
0x14009aebc  mov     [rsp+910h+lpdwBufferLength], rax; lpdwBufferLength
0x14009aec1  mov     r9, r13; lpBuffer
0x14009aec4  xor     r8d, r8d; pwszName
0x14009aec7  lea     edx, [r8+15h]; dwInfoLevel
0x14009aecb  mov     rcx, rdi; hRequest
0x14009aece  call    cs:__imp_WinHttpQueryHeaders
0x14009aed4  test    eax, eax
0x14009aed6  jz      loc_14009AFE0
0x14009aedc  xorps   xmm0, xmm0
0x14009aedf  movups  [rbp+810h+var_870], xmm0
0x14009aee3  mov     [rbp+810h+var_860], r15
0x14009aee7  mov     [rbp+810h+var_858], r15
0x14009aeeb  mov     r8, r14
0x14009aeee  mov     rdx, r13
0x14009aef1  lea     rcx, [rbp+810h+var_870]
0x14009aef5  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x14009aefa  nop
0x14009aefb  lea     rdx, [rbp+810h+var_870]
0x14009aeff  lea     rcx, [rsp+910h+var_8A0]
0x14009af04  call    ?ParseHeaders@@YA?AV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; ParseHeaders(std::wstring const &)
0x14009af09  mov     r12, rax
0x14009af0c  mov     rsi, [rsi]
0x14009af0f  add     rsi, 28h ; '('
0x14009af13  cmp     rsi, rax
0x14009af16  jz      short loc_14009AF8F
0x14009af18  mov     r14, [rsi]
0x14009af1b  mov     r15, [r14+8]
0x14009af1f  jmp     short loc_14009AF55
0x14009af21  mov     r8, [r15+10h]
0x14009af25  mov     rdx, rsi
0x14009af28  mov     rcx, rsi
0x14009af2b  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>>>(std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>> &,std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *> *)
0x14009af30  mov     rdi, r15
0x14009af33  mov     r15, [r15]
0x14009af36  lea     rcx, [rdi+40h]
0x14009af3a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14009af3f  lea     rcx, [rdi+20h]
0x14009af43  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14009af48  mov     edx, 60h ; '`'; unsigned __int64
0x14009af4d  mov     rcx, rdi; void *
0x14009af50  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14009af55  cmp     byte ptr [r15+19h], 0
0x14009af5a  jz      short loc_14009AF21
0x14009af5c  mov     [r14+8], r14
0x14009af60  mov     [r14], r14
0x14009af63  mov     [r14+10h], r14
0x14009af67  mov     qword ptr [rsi+8], 0
0x14009af6f  mov     rcx, [rsi]
0x14009af72  mov     rax, [r12]
0x14009af76  mov     [rsi], rax
0x14009af79  mov     [r12], rcx
0x14009af7d  mov     rcx, [rsi+8]
0x14009af81  mov     rax, [r12+8]
0x14009af86  mov     [rsi+8], rax
0x14009af8a  mov     [r12+8], rcx
0x14009af8f  lea     rcx, [rsp+910h+var_8A0]
0x14009af94  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(void)
0x14009af99  nop
0x14009af9a  lea     rcx, [rbp+810h+var_870]
0x14009af9e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14009afa3  nop
0x14009afa4  mov     rcx, r13; void *
0x14009afa7  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14009afac  nop
0x14009afad  lea     rcx, [rbp+810h+Src]
0x14009afb1  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x14009afb6  mov     rcx, [rbp+810h+var_40]
0x14009afbd  xor     rcx, rsp; StackCookie
0x14009afc0  call    __security_check_cookie
0x14009afc5  mov     rbx, [rsp+910h+arg_10]
0x14009afcd  add     rsp, 8E0h
0x14009afd4  pop     r15
0x14009afd6  pop     r14
0x14009afd8  pop     r13
0x14009afda  pop     r12
0x14009afdc  pop     rdi
0x14009afdd  pop     rsi
0x14009afde  pop     rbp
0x14009afdf  retn
0x14009afe0  call    cs:__imp_GetLastError
0x14009afe6  nop
0x14009afe7  mov     ebx, eax
0x14009afe9  test    eax, eax
0x14009afeb  jle     short loc_14009AFF6
0x14009afed  movzx   ebx, ax
0x14009aff0  or      ebx, 80070000h
0x14009aff6  lea     rax, WPP_GLOBAL_Control
0x14009affd  mov     rcx, cs:WPP_GLOBAL_Control
0x14009b004  cmp     rcx, rax
0x14009b007  jz      short loc_14009B027
0x14009b009  test    byte ptr [rcx+1Ch], 1
0x14009b00d  jz      short loc_14009B027
0x14009b00f  mov     edx, 14h
0x14009b014  mov     r9d, ebx
0x14009b017  lea     r8, WPP_b4f7f3e5d1fd340cfdb1f1c040853efe_Traceguids
0x14009b01e  mov     rcx, [rcx+10h]
0x14009b022  call    WPP_SF_d
0x14009b027  mov     edx, ebx; int
0x14009b029  lea     rcx, [rsp+910h+pExceptionObject]; this
0x14009b02e  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x14009b033  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x14009b03a  lea     rcx, [rsp+910h+pExceptionObject]; pExceptionObject
0x14009b03f  call    _CxxThrowException_0
0x14009b045  call    cs:__imp_GetLastError
0x14009b04b  mov     ebx, eax
0x14009b04d  test    eax, eax
0x14009b04f  jle     short loc_14009B05A
0x14009b051  movzx   ebx, ax
0x14009b054  or      ebx, 80070000h
0x14009b05a  lea     rax, WPP_GLOBAL_Control
0x14009b061  mov     rcx, cs:WPP_GLOBAL_Control
0x14009b068  cmp     rcx, rax
0x14009b06b  jz      short loc_14009B08B
0x14009b06d  test    byte ptr [rcx+1Ch], 1
0x14009b071  jz      short loc_14009B08B
0x14009b073  mov     edx, 12h
0x14009b078  mov     r9d, ebx
0x14009b07b  lea     r8, WPP_b4f7f3e5d1fd340cfdb1f1c040853efe_Traceguids
0x14009b082  mov     rcx, [rcx+10h]
0x14009b086  call    WPP_SF_d
0x14009b08b  mov     edx, ebx; int
0x14009b08d  lea     rcx, [rsp+910h+pExceptionObject]; this
0x14009b092  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x14009b097  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x14009b09e  lea     rcx, [rsp+910h+pExceptionObject]; pExceptionObject
0x14009b0a3  call    _CxxThrowException_0
0x14009b0a9  call    cs:__imp_GetLastError
0x14009b0af  mov     ebx, eax
0x14009b0b1  test    eax, eax
0x14009b0b3  jle     short loc_14009B0BE
0x14009b0b5  movzx   ebx, ax
0x14009b0b8  or      ebx, 80070000h
0x14009b0be  lea     rax, WPP_GLOBAL_Control
0x14009b0c5  mov     rcx, cs:WPP_GLOBAL_Control
0x14009b0cc  cmp     rcx, rax
0x14009b0cf  jz      short loc_14009B0EF
0x14009b0d1  test    byte ptr [rcx+1Ch], 1
0x14009b0d5  jz      short loc_14009B0EF
0x14009b0d7  mov     edx, 11h
0x14009b0dc  mov     r9d, ebx
0x14009b0df  lea     r8, WPP_b4f7f3e5d1fd340cfdb1f1c040853efe_Traceguids
0x14009b0e6  mov     rcx, [rcx+10h]
0x14009b0ea  call    WPP_SF_d
0x14009b0ef  mov     edx, ebx; int
0x14009b0f1  lea     rcx, [rbp+810h+var_870]; this
0x14009b0f5  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x14009b0fa  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x14009b101  lea     rcx, [rbp+810h+var_870]; pExceptionObject
0x14009b105  call    _CxxThrowException_0
0x14009b10b  jle     short loc_14009B116
0x14009b10d  movzx   ebx, ax
0x14009b110  or      ebx, 80070000h
0x14009b116  lea     rax, WPP_GLOBAL_Control
0x14009b11d  mov     rcx, cs:WPP_GLOBAL_Control
0x14009b124  cmp     rcx, rax
0x14009b127  jz      short loc_14009B147
0x14009b129  test    byte ptr [rcx+1Ch], 1
0x14009b12d  jz      short loc_14009B147
0x14009b12f  mov     edx, 13h
0x14009b134  mov     r9d, ebx
0x14009b137  lea     r8, WPP_b4f7f3e5d1fd340cfdb1f1c040853efe_Traceguids
0x14009b13e  mov     rcx, [rcx+10h]
0x14009b142  call    WPP_SF_d
0x14009b147  mov     edx, ebx; int
0x14009b149  lea     rcx, [rsp+910h+pExceptionObject]; this
0x14009b14e  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x14009b153  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x14009b15a  lea     rcx, [rsp+910h+pExceptionObject]; pExceptionObject
0x14009b15f  call    _CxxThrowException_0
```
