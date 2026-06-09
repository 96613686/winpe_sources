# W3_STATIC_FILE_HANDLER::CacheValidationDoWork(IHttpContext *,IHttpFileInfo *,int *)

- ea: `0x180004ed8`
- end: `0x180005227`
- name: `?CacheValidationDoWork@W3_STATIC_FILE_HANDLER@@SAJPEAVIHttpContext@@PEAVIHttpFileInfo@@PEAH@Z`
- size: `847`
- prototype: `__int64 __fastcall(struct IHttpContext *, struct IHttpFileInfo *, int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180002dd8`

## callees

- `0x180004ed8`
- `0x180005230`
- `0x180007010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180005089`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180005089`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005122`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005122`
- `iisutil!StringTimeToFileTime` at `0x180005056`
- `iisutil!StringTimeToFileTime` at `0x1800050c7`
- `iisutil!StringTimeToFileTime` at `0x180005056`
- `iisutil!StringTimeToFileTime` at `0x1800050c7`

## pseudocode

```c
__int64 __fastcall W3_STATIC_FILE_HANDLER::CacheValidationDoWork(
        struct IHttpContext *a1,
        struct IHttpFileInfo *a2,
        int *a3)
{
  __int64 v6; // rdi
  __int64 v7; // r14
  int v8; // r13d
  const char *v9; // rbx
  __int64 v10; // rax
  int v11; // r12d
  const char *v12; // rax
  const char *v13; // rax
  __int64 v14; // rax
  const char *v15; // rax
  __int64 v16; // rax
  __int64 v17; // rax
  const char *v18; // r8
  __int64 v19; // rdx
  signed int LastError; // eax
  unsigned int v21; // esi
  __int64 v22; // rcx
  void (__fastcall *v23)(__int64, __int64, const char *, _QWORD, unsigned int, _QWORD, _DWORD); // rax
  __int64 v24; // rax
  unsigned int v26; // [rsp+20h] [rbp-30h]
  union _LARGE_INTEGER v27[2]; // [rsp+40h] [rbp-10h] BYREF
  char *v28; // [rsp+90h] [rbp+40h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+A8h] [rbp+58h] BYREF

  v6 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a1 + 32LL))(a1);
  v7 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a1 + 24LL))(a1);
  v8 = 0;
  v9 = (const char *)(*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v7 + 16LL))(v7, 29);
  if ( !v9
    || ((v10 = (*(__int64 (__fastcall **)(struct IHttpFileInfo *, _QWORD))(*(_QWORD *)a2 + 96LL))(a2, 0),
         *(_BYTE *)v10 != 87)
     || *(_BYTE *)(v10 + 1) != 47)
    && (unsigned int)FindInETagList((const char *)v10, v9, 0) )
  {
    v28 = (char *)(*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v7 + 16LL))(v7, 31);
    v11 = 1;
    if ( v28 )
    {
      v12 = (const char *)(*(__int64 (__fastcall **)(struct IHttpFileInfo *, _QWORD))(*(_QWORD *)a2 + 96LL))(a2, 0);
      if ( (unsigned int)FindInETagList(v12, v28, 1) )
        v11 = 0;
      else
        v8 = 1;
    }
    LODWORD(v28) = *(_DWORD *)((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v7 + 8LL))(v7) + 36);
    v13 = (const char *)(*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v7 + 16LL))(v7, 30);
    if ( v8 || !v13 )
    {
      if ( v11 )
        goto LABEL_15;
    }
    else
    {
      v27[0].QuadPart = 0;
      if ( !StringTimeToFileTime(v13, v27) )
        goto LABEL_19;
      v14 = *(_QWORD *)a2;
      SystemTimeAsFileTime = 0;
      (*(void (__fastcall **)(struct IHttpFileInfo *, struct _FILETIME *))(v14 + 104))(a2, &SystemTimeAsFileTime);
      if ( *(_QWORD *)&SystemTimeAsFileTime > v27[0].QuadPart
        || (GetSystemTimeAsFileTime(&SystemTimeAsFileTime), *(_QWORD *)&SystemTimeAsFileTime < v27[0].QuadPart) )
      {
LABEL_15:
        v15 = (const char *)(*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v7 + 16LL))(v7, 33);
        if ( !v15 )
          goto LABEL_29;
        v28 = 0;
        if ( StringTimeToFileTime(v15, (union _LARGE_INTEGER *)&v28) )
        {
          v16 = *(_QWORD *)a2;
          SystemTimeAsFileTime = 0;
          (*(void (__fastcall **)(struct IHttpFileInfo *, struct _FILETIME *))(v16 + 104))(a2, &SystemTimeAsFileTime);
          if ( *(_QWORD *)&SystemTimeAsFileTime > (__int64)v28 )
          {
            v17 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v6 + 8LL))(v6);
            v18 = "Precondition Failed";
            v19 = 412;
            v26 = 0;
LABEL_22:
            *(_WORD *)(v17 + 536) = 0;
            v22 = v6;
            v23 = *(void (__fastcall **)(__int64, __int64, const char *, _QWORD, unsigned int, _QWORD, _DWORD))(*(_QWORD *)v6 + 24LL);
            goto LABEL_23;
          }
LABEL_29:
          *a3 = 0;
          return 0;
        }
LABEL_19:
        LastError = GetLastError();
        v21 = LastError;
        if ( LastError > 0 )
          v21 = (unsigned __int16)LastError | 0x80070000;
        v17 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v6 + 8LL))(v6);
        v18 = "Bad Request";
        v19 = 400;
        v26 = v21;
        goto LABEL_22;
      }
    }
    v24 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v6 + 8LL))(v6);
    v22 = v6;
    v26 = 0;
    *(_QWORD *)(v24 + 272) = 0;
    *(_WORD *)(v24 + 264) = 0;
    v23 = *(void (__fastcall **)(__int64, __int64, const char *, _QWORD, unsigned int, _QWORD, _DWORD))(*(_QWORD *)v6 + 24LL);
    if ( (unsigned int)((_DWORD)v28 - 4) <= 1 )
    {
      v23(v6, 304, "Not Modified", 0, 0, 0, 0);
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v6 + 48LL))(v6, 19);
      goto LABEL_24;
    }
    v19 = 412;
    v18 = "Precondition Failed";
LABEL_23:
    v23(v22, v19, v18, 0, v26, 0, 0);
LABEL_24:
    *a3 = 1;
    return 0;
  }
  *(_WORD *)((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v6 + 8LL))(v6) + 536) = 0;
  (*(void (__fastcall **)(__int64, __int64, const char *, _QWORD, _DWORD, _QWORD, _DWORD))(*(_QWORD *)v6 + 24LL))(
    v6,
    412,
    "Precondition Failed",
    0,
    0,
    0,
    0);
  *a3 = 1;
  return 0;
}

```

## disassembly

```asm
0x180004ed8  mov     [rsp-38h+arg_8], rbx
0x180004edd  push    rbp
0x180004ede  push    rsi
0x180004edf  push    rdi
0x180004ee0  push    r12
0x180004ee2  push    r13
0x180004ee4  push    r14
0x180004ee6  push    r15
0x180004ee8  mov     rbp, rsp
0x180004eeb  sub     rsp, 50h
0x180004eef  mov     rax, [rcx]
0x180004ef2  mov     r15, r8
0x180004ef5  mov     rsi, rdx
0x180004ef8  mov     rbx, rcx
0x180004efb  mov     rax, [rax+20h]
0x180004eff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004f04  mov     r9, [rbx]
0x180004f07  mov     rdi, rax
0x180004f0a  mov     rcx, rbx
0x180004f0d  mov     rax, [r9+18h]
0x180004f11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004f16  mov     r14, rax
0x180004f19  xor     r8d, r8d
0x180004f1c  mov     rcx, [rax]
0x180004f1f  lea     edx, [r8+1Dh]
0x180004f23  mov     rax, [rcx+10h]
0x180004f27  mov     rcx, r14
0x180004f2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004f2f  xor     r13d, r13d
0x180004f32  mov     rbx, rax
0x180004f35  test    rax, rax
0x180004f38  jz      short loc_180004FB8
0x180004f3a  mov     rcx, [rsi]
0x180004f3d  xor     edx, edx
0x180004f3f  mov     rax, [rcx+60h]
0x180004f43  mov     rcx, rsi
0x180004f46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004f4b  cmp     byte ptr [rax], 57h ; 'W'
0x180004f4e  jnz     short loc_180004F56
0x180004f50  cmp     byte ptr [rax+1], 2Fh ; '/'
0x180004f54  jz      short loc_180004F68
0x180004f56  xor     r8d, r8d; int
0x180004f59  mov     rdx, rbx; char *
0x180004f5c  mov     rcx, rax; char *
0x180004f5f  call    ?FindInETagList@@YAHPEBD0H@Z; FindInETagList(char const *,char const *,int)
0x180004f64  test    eax, eax
0x180004f66  jnz     short loc_180004FB8
0x180004f68  mov     rax, [rdi]
0x180004f6b  mov     rcx, rdi
0x180004f6e  mov     rax, [rax+8]
0x180004f72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004f77  mov     [rsp+50h+var_20], r13d
0x180004f7c  lea     r8, aPreconditionFa; "Precondition Failed"
0x180004f83  xor     r9d, r9d
0x180004f86  mov     [rsp+50h+var_28], r13
0x180004f8b  mov     edx, 19Ch
0x180004f90  mov     [rsp+50h+var_30], r13d
0x180004f95  mov     [rax+218h], r13w
0x180004f9d  mov     rcx, rdi
0x180004fa0  mov     rax, [rdi]
0x180004fa3  mov     rax, [rax+18h]
0x180004fa7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004fac  mov     dword ptr [r15], 1
0x180004fb3  jmp     loc_18000520D
0x180004fb8  mov     rax, [r14]
0x180004fbb  xor     r8d, r8d
0x180004fbe  mov     rcx, r14
0x180004fc1  mov     rax, [rax+10h]
0x180004fc5  lea     edx, [r8+1Fh]
0x180004fc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004fce  mov     [rbp+arg_0], rax
0x180004fd2  mov     ebx, 1
0x180004fd7  mov     r12d, ebx
0x180004fda  test    rax, rax
0x180004fdd  jz      short loc_18000500B
0x180004fdf  mov     rcx, [rsi]
0x180004fe2  xor     edx, edx
0x180004fe4  mov     rax, [rcx+60h]
0x180004fe8  mov     rcx, rsi
0x180004feb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004ff0  mov     rdx, [rbp+arg_0]; char *
0x180004ff4  mov     rcx, rax; char *
0x180004ff7  mov     r8d, ebx; int
0x180004ffa  call    ?FindInETagList@@YAHPEBD0H@Z; FindInETagList(char const *,char const *,int)
0x180004fff  test    eax, eax
0x180005001  jz      short loc_180005008
0x180005003  xor     r12d, r12d
0x180005006  jmp     short loc_18000500B
0x180005008  mov     r13d, ebx
0x18000500b  mov     rax, [r14]
0x18000500e  mov     rcx, r14
0x180005011  mov     rax, [rax+8]
0x180005015  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000501a  xor     r8d, r8d
0x18000501d  mov     rcx, r14
0x180005020  mov     eax, [rax+24h]
0x180005023  mov     dword ptr [rbp+arg_0], eax
0x180005026  lea     edx, [r8+1Eh]
0x18000502a  mov     rax, [r14]
0x18000502d  mov     rax, [rax+10h]
0x180005031  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005036  test    r13d, r13d
0x180005039  jnz     loc_180005182
0x18000503f  xor     r13d, r13d
0x180005042  test    rax, rax
0x180005045  jz      loc_180005185
0x18000504b  lea     rdx, [rbp+var_10]
0x18000504f  mov     qword ptr [rbp+var_10], r13
0x180005053  mov     rcx, rax
0x180005056  call    cs:__imp_?StringTimeToFileTime@@YAHPEBDPEAT_LARGE_INTEGER@@@Z; StringTimeToFileTime(char const *,_LARGE_INTEGER *)
0x18000505c  test    eax, eax
0x18000505e  jz      loc_180005122
0x180005064  mov     rax, [rsi]
0x180005067  lea     rdx, [rbp+SystemTimeAsFileTime]
0x18000506b  mov     rcx, rsi
0x18000506e  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], r13
0x180005072  mov     rax, [rax+68h]
0x180005076  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000507b  mov     rax, qword ptr [rbp+var_10]
0x18000507f  cmp     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180005083  jg      short loc_18000509D
0x180005085  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180005089  call    cs:__imp_GetSystemTimeAsFileTime
0x18000508f  mov     rax, qword ptr [rbp+var_10]
0x180005093  cmp     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180005097  jge     loc_18000518E
0x18000509d  mov     rax, [r14]
0x1800050a0  xor     r8d, r8d
0x1800050a3  mov     rcx, r14
0x1800050a6  mov     rax, [rax+10h]
0x1800050aa  lea     edx, [r8+21h]
0x1800050ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800050b3  test    rax, rax
0x1800050b6  jz      loc_18000520A
0x1800050bc  lea     rdx, [rbp+arg_0]
0x1800050c0  mov     [rbp+arg_0], r13
0x1800050c4  mov     rcx, rax
0x1800050c7  call    cs:__imp_?StringTimeToFileTime@@YAHPEBDPEAT_LARGE_INTEGER@@@Z; StringTimeToFileTime(char const *,_LARGE_INTEGER *)
0x1800050cd  test    eax, eax
0x1800050cf  jz      short loc_180005122
0x1800050d1  mov     rax, [rsi]
0x1800050d4  lea     rdx, [rbp+SystemTimeAsFileTime]
0x1800050d8  mov     rcx, rsi
0x1800050db  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], r13
0x1800050df  mov     rax, [rax+68h]
0x1800050e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800050e8  mov     rax, [rbp+arg_0]
0x1800050ec  cmp     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1800050f0  jle     loc_18000520A
0x1800050f6  mov     rax, [rdi]
0x1800050f9  mov     rcx, rdi
0x1800050fc  mov     rax, [rax+8]
0x180005100  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005105  mov     [rsp+50h+var_20], r13d
0x18000510a  lea     r8, aPreconditionFa; "Precondition Failed"
0x180005111  mov     [rsp+50h+var_28], r13
0x180005116  mov     edx, 19Ch
0x18000511b  mov     [rsp+50h+var_30], r13d
0x180005120  jmp     short loc_180005160
0x180005122  call    cs:__imp_GetLastError
0x180005128  mov     esi, eax
0x18000512a  test    eax, eax
0x18000512c  jle     short loc_180005137
0x18000512e  movzx   esi, ax
0x180005131  or      esi, 80070000h
0x180005137  mov     rax, [rdi]
0x18000513a  mov     rcx, rdi
0x18000513d  mov     rax, [rax+8]
0x180005141  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005146  mov     [rsp+50h+var_20], r13d
0x18000514b  lea     r8, aBadRequest; "Bad Request"
0x180005152  mov     [rsp+50h+var_28], r13
0x180005157  mov     edx, 190h
0x18000515c  mov     [rsp+50h+var_30], esi
0x180005160  mov     [rax+218h], r13w
0x180005168  xor     r9d, r9d
0x18000516b  mov     rax, [rdi]
0x18000516e  mov     rcx, rdi
0x180005171  mov     rax, [rax+18h]
0x180005175  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000517a  mov     [r15], ebx
0x18000517d  jmp     loc_18000520D
0x180005182  xor     r13d, r13d
0x180005185  test    r12d, r12d
0x180005188  jnz     loc_18000509D
0x18000518e  mov     rax, [rdi]
0x180005191  mov     rcx, rdi
0x180005194  mov     rax, [rax+8]
0x180005198  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000519d  mov     [rsp+50h+var_20], r13d
0x1800051a2  xor     r9d, r9d
0x1800051a5  mov     [rsp+50h+var_28], r13
0x1800051aa  mov     rcx, rdi
0x1800051ad  mov     [rsp+50h+var_30], r13d
0x1800051b2  mov     [rax+110h], r13
0x1800051b9  mov     [rax+108h], r13w
0x1800051c1  mov     eax, dword ptr [rbp+arg_0]
0x1800051c4  add     eax, 0FFFFFFFCh
0x1800051c7  cmp     eax, ebx
0x1800051c9  mov     rax, [rdi]
0x1800051cc  mov     rax, [rax+18h]
0x1800051d0  jbe     short loc_1800051E0
0x1800051d2  mov     edx, 19Ch
0x1800051d7  lea     r8, aPreconditionFa; "Precondition Failed"
0x1800051de  jmp     short loc_180005175
0x1800051e0  lea     r8, aNotModified; "Not Modified"
0x1800051e7  mov     edx, 130h
0x1800051ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800051f1  mov     rax, [rdi]
0x1800051f4  mov     edx, 13h
0x1800051f9  mov     rcx, rdi
0x1800051fc  mov     rax, [rax+30h]
0x180005200  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005205  jmp     loc_18000517A
0x18000520a  mov     [r15], r13d
0x18000520d  mov     rbx, [rsp+50h+arg_8]
0x180005215  xor     eax, eax
0x180005217  add     rsp, 50h
0x18000521b  pop     r15
0x18000521d  pop     r14
0x18000521f  pop     r13
0x180005221  pop     r12
0x180005223  pop     rdi
0x180005224  pop     rsi
0x180005225  pop     rbp
0x180005226  retn
```
