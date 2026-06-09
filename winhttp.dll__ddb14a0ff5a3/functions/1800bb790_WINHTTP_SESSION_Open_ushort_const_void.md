# WINHTTP_SESSION::Open(ushort const *,void *)

- ea: `0x1800bb790`
- end: `0x1800bb9c6`
- name: `?Open@WINHTTP_SESSION@@MEAAHPEBGPEAX@Z`
- size: `566`
- prototype: `__int64 __fastcall(WINHTTP_SESSION *__hidden this, const unsigned __int16 *, void *)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x1800a1d10`
- `0x1800b91a0`
- `0x1800bb4a4`
- `0x1800bb790`
- `0x1800cf008`
- `0x1800dbccc`
- `0x1800de010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800bb7da`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800bb7da`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800bb977`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800bb977`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bb7f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bb8f2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bb7f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bb8f2`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800bb8d3`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800bb8de`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800bb8d3`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800bb8de`

## string_xrefs

- `0x1800bb8a5`: `Microsoft-WinHttp-Passport-Authentication-Service/1.4`

## pseudocode

```c
__int64 __fastcall WINHTTP_SESSION::Open(
        WINHTTP_SESSION *this,
        void *(*a2)(const unsigned __int16 *, unsigned int, const unsigned __int16 *, const unsigned __int16 *, unsigned int),
        void *(*a3)(const unsigned __int16 *, unsigned int, const unsigned __int16 *, const unsigned __int16 *, unsigned int))
{
  unsigned int v6; // r14d
  HMODULE Library; // rax
  HMODULE *v8; // r15
  char LastError; // al
  int v10; // edx
  HGLOBAL v11; // r8
  __int64 v12; // rdx
  void (*v13)(void); // rax
  void *(*v15[5])(const unsigned __int16 *, unsigned int, const unsigned __int16 *, const unsigned __int16 *, unsigned int); // [rsp+38h] [rbp-80h] BYREF
  __int64 v16; // [rsp+60h] [rbp-58h] BYREF
  HGLOBAL hMem[2]; // [rsp+68h] [rbp-50h]
  int v18; // [rsp+78h] [rbp-40h] BYREF

  v15[1] = (void *(*)(const unsigned __int16 *, unsigned int, const unsigned __int16 *, const unsigned __int16 *, unsigned int))this;
  v15[2] = a2;
  v15[3] = a3;
  v6 = 0;
  v15[0] = 0;
  Library = LoadLibraryExW((LPCWSTR)a2, 0, 0);
  v8 = (HMODULE *)((char *)this + 8);
  v15[4] = (void *(*)(const unsigned __int16 *, unsigned int, const unsigned __int16 *, const unsigned __int16 *, unsigned int))((char *)this + 8);
  *((_QWORD *)this + 1) = Library;
  if ( !Library )
  {
    LastError = GetLastError();
    if ( (BYTE1(xmmword_180107A50) & 4) == 0 )
      goto LABEL_15;
    v10 = 25;
    goto LABEL_4;
  }
  if ( (unsigned int)WINHTTP_SESSION::InitHttpApi(this, v15) )
  {
    v16 = 0;
    *(_OWORD *)hMem = 0;
    v18 = 24;
    if ( (*(unsigned int (__fastcall **)(WINHTTP_SESSION *, void *(*)(const unsigned __int16 *, unsigned int, const unsigned __int16 *, const unsigned __int16 *, unsigned int), __int64, __int64 *, int *))(*(_QWORD *)this + 72LL))(
           this,
           a3,
           38,
           &v16,
           &v18) )
    {
      v11 = hMem[0];
      v12 = (unsigned int)v16;
    }
    else
    {
      v11 = 0;
      v12 = 0;
    }
    *((_QWORD *)this + 4) = ((__int64 (__fastcall *)(const wchar_t *, __int64, HGLOBAL, _QWORD, _DWORD))v15[0])(
                              L"Microsoft-WinHttp-Passport-Authentication-Service/1.4",
                              v12,
                              v11,
                              0,
                              0);
    GlobalFree(hMem[0]);
    GlobalFree(hMem[1]);
    *((_DWORD *)this + 5) = 1;
    if ( *((_QWORD *)this + 4) )
    {
      if ( (unsigned int)SESSION::Open(this, (const unsigned __int16 *)a2, a3) )
      {
        v6 = 1;
        if ( (BYTE1(xmmword_180107A60) & 4) != 0 )
          WPP_SF_(1034, 27, WPP_023169352d70318e9b1c2b0fcf19433c_Traceguids);
      }
    }
    else
    {
      LastError = GetLastError();
      if ( (BYTE1(xmmword_180107A50) & 4) != 0 )
      {
        v10 = 26;
LABEL_4:
        WPP_SF_Sd(522, v10, (unsigned int)WPP_023169352d70318e9b1c2b0fcf19433c_Traceguids, (_DWORD)a2, LastError);
      }
    }
  }
LABEL_15:
  if ( !v6 )
  {
    if ( *((_QWORD *)this + 4) )
    {
      if ( *((_DWORD *)this + 5) )
      {
        v13 = (void (*)(void))*((_QWORD *)this + 629);
        if ( v13 )
        {
          v13();
          *((_QWORD *)this + 4) = 0;
        }
      }
    }
    if ( *v8 )
    {
      FreeLibrary(*v8);
      *v8 = 0;
    }
    if ( (BYTE1(xmmword_180107A50) & 4) != 0 )
      WPP_SF_(522, 28, WPP_023169352d70318e9b1c2b0fcf19433c_Traceguids);
  }
  return v6;
}

```

## disassembly

```asm
0x1800bb790  push    rsi
0x1800bb792  push    rdi
0x1800bb793  push    r12
0x1800bb795  push    r14
0x1800bb797  push    r15
0x1800bb799  sub     rsp, 90h
0x1800bb7a0  mov     rax, cs:__security_cookie
0x1800bb7a7  xor     rax, rsp
0x1800bb7aa  mov     [rsp+0B8h+var_38], rax
0x1800bb7b2  mov     r12, r8
0x1800bb7b5  mov     rsi, rdx
0x1800bb7b8  mov     rdi, rcx
0x1800bb7bb  mov     [rsp+0B8h+var_78], rcx
0x1800bb7c0  mov     [rsp+0B8h+var_70], rdx
0x1800bb7c5  mov     [rsp+0B8h+var_68], r8
0x1800bb7ca  xor     r14d, r14d
0x1800bb7cd  mov     [rsp+0B8h+var_80], r14
0x1800bb7d2  xor     r8d, r8d; dwFlags
0x1800bb7d5  xor     edx, edx; hFile
0x1800bb7d7  mov     rcx, rsi; lpLibFileName
0x1800bb7da  call    cs:__imp_LoadLibraryExW
0x1800bb7e0  lea     r15, [rdi+8]
0x1800bb7e4  mov     [rsp+0B8h+var_60], r15
0x1800bb7e9  mov     [r15], rax
0x1800bb7ec  test    rax, rax
0x1800bb7ef  jnz     short loc_1800BB825
0x1800bb7f1  call    cs:__imp_GetLastError
0x1800bb7f7  test    byte ptr cs:xmmword_180107A50+1, 4
0x1800bb7fe  jz      loc_1800BB941
0x1800bb804  lea     edx, [r14+19h]
0x1800bb808  mov     ecx, 20Ah
0x1800bb80d  mov     dword ptr [rsp+0B8h+var_98], eax
0x1800bb811  mov     r9, rsi
0x1800bb814  lea     r8, WPP_023169352d70318e9b1c2b0fcf19433c_Traceguids
0x1800bb81b  call    WPP_SF_Sd
0x1800bb820  jmp     loc_1800BB941
0x1800bb825  lea     rdx, [rsp+0B8h+var_80]; void *(**)(const unsigned __int16 *, unsigned int, const unsigned __int16 *, const unsigned __int16 *, unsigned int)
0x1800bb82a  mov     rcx, rdi; this
0x1800bb82d  call    ?InitHttpApi@WINHTTP_SESSION@@IEAAHPEAP6APEAXPEBGK00K@Z@Z; WINHTTP_SESSION::InitHttpApi(void * (**)(ushort const *,ulong,ushort const *,ushort const *,ulong))
0x1800bb832  test    eax, eax
0x1800bb834  jz      loc_1800BB941
0x1800bb83a  mov     [rsp+0B8h+var_58], r14
0x1800bb83f  xorps   xmm0, xmm0
0x1800bb842  movdqu  xmmword ptr [rsp+0B8h+hMem], xmm0
0x1800bb848  mov     [rsp+0B8h+var_40], 18h
0x1800bb850  mov     rax, [rdi]
0x1800bb853  lea     rcx, [rsp+0B8h+var_40]
0x1800bb858  mov     [rsp+0B8h+var_98], rcx
0x1800bb85d  lea     r9, [rsp+0B8h+var_58]
0x1800bb862  mov     r8d, 26h ; '&'
0x1800bb868  mov     rdx, r12
0x1800bb86b  mov     rcx, rdi
0x1800bb86e  mov     rax, [rax+48h]
0x1800bb872  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bb877  mov     [rsp+0B8h+var_88], eax
0x1800bb87b  jmp     short loc_1800BB89A
0x1800bb87d  xor     eax, eax
0x1800bb87f  mov     [rsp+0B8h+var_88], eax
0x1800bb883  mov     r14d, eax
0x1800bb886  mov     rdi, [rsp+0B8h+var_78]
0x1800bb88b  mov     rsi, [rsp+0B8h+var_70]
0x1800bb890  mov     r12, [rsp+0B8h+var_68]
0x1800bb895  mov     r15, [rsp+0B8h+var_60]
0x1800bb89a  mov     dword ptr [rsp+0B8h+var_98], 0
0x1800bb8a2  xor     r9d, r9d
0x1800bb8a5  lea     rcx, aMicrosoftWinht; "Microsoft-WinHttp-Passport-Authenticati"...
0x1800bb8ac  test    eax, eax
0x1800bb8ae  mov     rax, [rsp+0B8h+var_80]
0x1800bb8b3  jnz     short loc_1800BB8BC
0x1800bb8b5  xor     r8d, r8d
0x1800bb8b8  xor     edx, edx
0x1800bb8ba  jmp     short loc_1800BB8C5
0x1800bb8bc  mov     r8, [rsp+0B8h+hMem]
0x1800bb8c1  mov     edx, dword ptr [rsp+0B8h+var_58]
0x1800bb8c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bb8ca  mov     [rdi+20h], rax
0x1800bb8ce  mov     rcx, [rsp+0B8h+hMem]; hMem
0x1800bb8d3  call    cs:__imp_GlobalFree
0x1800bb8d9  mov     rcx, [rsp+0B8h+hMem+8]; hMem
0x1800bb8de  call    cs:__imp_GlobalFree
0x1800bb8e4  mov     dword ptr [rdi+14h], 1
0x1800bb8eb  cmp     qword ptr [rdi+20h], 0
0x1800bb8f0  jnz     short loc_1800BB90B
0x1800bb8f2  call    cs:__imp_GetLastError
0x1800bb8f8  test    byte ptr cs:xmmword_180107A50+1, 4
0x1800bb8ff  jz      short loc_1800BB941
0x1800bb901  mov     edx, 1Ah
0x1800bb906  jmp     loc_1800BB808
0x1800bb90b  mov     r8, r12; void *
0x1800bb90e  mov     rdx, rsi; unsigned __int16 *
0x1800bb911  mov     rcx, rdi; this
0x1800bb914  call    ?Open@SESSION@@UEAAHPEBGPEAX@Z; SESSION::Open(ushort const *,void *)
0x1800bb919  test    eax, eax
0x1800bb91b  jz      short loc_1800BB941
0x1800bb91d  mov     r14d, 1
0x1800bb923  test    byte ptr cs:xmmword_180107A60+1, 4
0x1800bb92a  jz      short loc_1800BB941
0x1800bb92c  lea     edx, [r14+1Ah]
0x1800bb930  mov     ecx, 40Ah
0x1800bb935  lea     r8, WPP_023169352d70318e9b1c2b0fcf19433c_Traceguids
0x1800bb93c  call    WPP_SF_
0x1800bb941  test    r14d, r14d
0x1800bb944  jnz     short loc_1800BB9A3
0x1800bb946  mov     rcx, [rdi+20h]
0x1800bb94a  test    rcx, rcx
0x1800bb94d  jz      short loc_1800BB96E
0x1800bb94f  cmp     [rdi+14h], r14d
0x1800bb953  jz      short loc_1800BB96E
0x1800bb955  mov     rax, [rdi+13A8h]
0x1800bb95c  test    rax, rax
0x1800bb95f  jz      short loc_1800BB96E
0x1800bb961  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bb966  mov     qword ptr [rdi+20h], 0
0x1800bb96e  cmp     qword ptr [r15], 0
0x1800bb972  jz      short loc_1800BB984
0x1800bb974  mov     rcx, [r15]; hLibModule
0x1800bb977  call    cs:__imp_FreeLibrary
0x1800bb97d  mov     qword ptr [r15], 0
0x1800bb984  test    byte ptr cs:xmmword_180107A50+1, 4
0x1800bb98b  jz      short loc_1800BB9A3
0x1800bb98d  mov     edx, 1Ch
0x1800bb992  mov     ecx, 20Ah
0x1800bb997  lea     r8, WPP_023169352d70318e9b1c2b0fcf19433c_Traceguids
0x1800bb99e  call    WPP_SF_
0x1800bb9a3  mov     eax, r14d
0x1800bb9a6  mov     rcx, [rsp+0B8h+var_38]
0x1800bb9ae  xor     rcx, rsp; StackCookie
0x1800bb9b1  call    __security_check_cookie
0x1800bb9b6  add     rsp, 90h
0x1800bb9bd  pop     r15
0x1800bb9bf  pop     r14
0x1800bb9c1  pop     r12
0x1800bb9c3  pop     rdi
0x1800bb9c4  pop     rsi
0x1800bb9c5  retn
```
