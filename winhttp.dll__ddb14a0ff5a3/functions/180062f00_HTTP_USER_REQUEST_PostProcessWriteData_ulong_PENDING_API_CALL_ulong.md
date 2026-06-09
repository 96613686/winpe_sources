# HTTP_USER_REQUEST::_PostProcessWriteData(ulong,PENDING_API_CALL *,ulong *)

- ea: `0x180062f00`
- end: `0x18006317e`
- name: `?_PostProcessWriteData@HTTP_USER_REQUEST@@AEAAKKPEAVPENDING_API_CALL@@PEAK@Z`
- size: `638`
- prototype: `__int64 __fastcall(HTTP_USER_REQUEST *this, unsigned int, struct PENDING_API_CALL *, unsigned int *)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180039380`
- `0x1800969c0`

## callees

- `0x180062f00`
- `0x1800a1d10`
- `0x1800b75ec`
- `0x1800de010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180063100`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180063100`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180063112`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180063112`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800630c5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800630c5`
- `ntdll!EtwEventActivityIdControl` at `0x180063006`
- `ntdll!EtwEventActivityIdControl` at `0x180063039`
- `ntdll!EtwEventActivityIdControl` at `0x18006309c`
- `ntdll!EtwEventActivityIdControl` at `0x180063006`
- `ntdll!EtwEventActivityIdControl` at `0x180063039`
- `ntdll!EtwEventActivityIdControl` at `0x18006309c`

## pseudocode

```c
__int64 __fastcall HTTP_USER_REQUEST::_PostProcessWriteData(
        HTTP_USER_REQUEST *this,
        unsigned int a2,
        struct PENDING_API_CALL *a3,
        unsigned int *a4)
{
  unsigned int v6; // edi
  __int64 v9; // rcx
  __int128 *v10; // rax
  __int64 v11; // rdx
  __int128 *v12; // rax
  __int64 v13; // rdx
  _BYTE *v14; // rax
  int v15; // eax
  bool v16; // sf
  int v17; // eax
  bool v18; // sf
  __int64 v19; // rdx
  __int64 v20; // rcx
  void (__fastcall *v21)(__int64, __int64, __int64, _DWORD *, int); // rax
  int v22; // eax
  bool v23; // sf
  int v24; // ebx
  void *v25; // rcx
  _DWORD v26[4]; // [rsp+30h] [rbp-39h] BYREF
  int v27[4]; // [rsp+40h] [rbp-29h] BYREF
  __int128 v28; // [rsp+50h] [rbp-19h] BYREF
  int v29; // [rsp+60h] [rbp-9h]
  _OWORD v30[2]; // [rsp+70h] [rbp+7h] BYREF

  v26[0] = 0;
  v27[0] = 0;
  v6 = a2;
  if ( a2 == 12030 )
  {
    if ( !*((_DWORD *)this + 2671) )
      return v6;
    WEBIO_REQUEST::GetHttp11DowngradeResendRequired(*((WEBIO_REQUEST **)a3 + 16), v27);
    if ( !v27[0] )
      return v6;
    v6 = 0;
    *a4 = *((_DWORD *)a3 + 24);
  }
  else if ( a2 )
  {
    return v6;
  }
  if ( (*((_BYTE *)a3 + 56) & 0x30) != 0 )
  {
    v26[0] = *a4;
    v28 = 0;
    v29 = 0;
    if ( !*((_DWORD *)a3 + 10) || (v24 = *((_DWORD *)a3 + 11), GetCurrentThreadId() == v24) )
    {
      v9 = 16;
      v10 = &v28;
      v11 = 16;
      do
      {
        *(_BYTE *)v10 = 0;
        v10 = (__int128 *)((char *)v10 + 1);
        --v11;
      }
      while ( v11 );
      v29 = 0;
      v12 = &v28;
      v13 = 16;
      memset(v30, 0, sizeof(v30));
      do
      {
        *(_BYTE *)v12 = 0;
        v12 = (__int128 *)((char *)v12 + 1);
        --v13;
      }
      while ( v13 );
      *(_OWORD *)v27 = 0;
      v14 = v30;
      do
      {
        *v14++ = 0;
        --v9;
      }
      while ( v9 );
      v15 = EtwEventActivityIdControl(1, v27);
      v16 = v15 < 0;
      if ( v15 > 0 )
        v16 = 1;
      if ( v16 )
        v27[1] = 128;
      else
        v30[0] = *(_OWORD *)v27;
      v27[1] = 0;
      v17 = EtwEventActivityIdControl(2, &WinHttpEtwNullActivityId);
      v18 = v17 < 0;
      if ( v17 > 0 )
        v18 = 1;
      if ( v18 )
        v27[1] = 144;
      v19 = *((_QWORD *)a3 + 8);
      v20 = *((_QWORD *)this + 4);
      v21 = (void (__fastcall *)(__int64, __int64, __int64, _DWORD *, int))*((_QWORD *)a3 + 6);
      v28 = v30[0];
      v29 = 1;
      v21(v20, v19, 32, v26, 4);
      if ( v29 )
      {
        v27[1] = 0;
        v22 = EtwEventActivityIdControl(2, &v28);
        v23 = v22 < 0;
        if ( v22 > 0 )
          v23 = 1;
        if ( v23 )
          v27[1] = 144;
      }
    }
    else
    {
      v25 = (void *)*((_QWORD *)a3 + 9);
      *((_QWORD *)a3 + 19) = v26;
      *((_DWORD *)a3 + 35) = 1;
      *((_DWORD *)a3 + 36) = 32;
      *((_DWORD *)a3 + 40) = 4;
      SetEvent(v25);
      WaitForSingleObjectEx(*((HANDLE *)a3 + 10), 0xFFFFFFFF, 0);
      *(_QWORD *)((char *)a3 + 140) = 0;
      *((_QWORD *)a3 + 19) = 0;
      *((_DWORD *)a3 + 40) = 0;
    }
  }
  return v6;
}

```

## disassembly

```asm
0x180062f00  mov     [rsp-8+arg_8], rbx
0x180062f05  push    rbp
0x180062f06  push    rsi
0x180062f07  push    rdi
0x180062f08  push    r14
0x180062f0a  push    r15
0x180062f0c  lea     rbp, [rsp-37h]
0x180062f11  sub     rsp, 0A0h
0x180062f18  mov     rax, cs:__security_cookie
0x180062f1f  xor     rax, rsp
0x180062f22  mov     [rbp+57h+var_30], rax
0x180062f26  xor     r15d, r15d
0x180062f29  mov     rbx, r9
0x180062f2c  mov     [rbp+57h+var_90], r15d
0x180062f30  mov     rsi, r8
0x180062f33  mov     [rbp+57h+var_80], r15d
0x180062f37  mov     edi, edx
0x180062f39  mov     r14, rcx
0x180062f3c  cmp     edx, 2EFEh
0x180062f42  jz      loc_180063132
0x180062f48  test    edx, edx
0x180062f4a  jnz     short loc_180062F52
0x180062f4c  test    byte ptr [rsi+38h], 30h
0x180062f50  jnz     short loc_180062F77
0x180062f52  mov     eax, edi
0x180062f54  mov     rcx, [rbp+57h+var_30]
0x180062f58  xor     rcx, rsp; StackCookie
0x180062f5b  call    __security_check_cookie
0x180062f60  mov     rbx, [rsp+0C0h+arg_8]
0x180062f68  add     rsp, 0A0h
0x180062f6f  pop     r15
0x180062f71  pop     r14
0x180062f73  pop     rdi
0x180062f74  pop     rsi
0x180062f75  pop     rbp
0x180062f76  retn
0x180062f77  mov     eax, [rbx]
0x180062f79  xorps   xmm0, xmm0
0x180062f7c  mov     [rbp+57h+var_90], eax
0x180062f7f  xor     eax, eax
0x180062f81  movups  [rbp+57h+var_70], xmm0
0x180062f85  mov     [rbp+57h+var_60], eax
0x180062f88  cmp     [rsi+28h], eax
0x180062f8b  jnz     loc_1800630C2
0x180062f91  mov     ecx, 10h
0x180062f96  lea     rax, [rbp+57h+var_70]
0x180062f9a  mov     edx, ecx
0x180062f9c  nop     dword ptr [rax+00h]
0x180062fa0  mov     [rax], r15b
0x180062fa3  lea     rax, [rax+1]
0x180062fa7  sub     rdx, 1
0x180062fab  jnz     short loc_180062FA0
0x180062fad  xorps   xmm0, xmm0
0x180062fb0  mov     [rbp+57h+var_60], r15d
0x180062fb4  xorps   xmm1, xmm1
0x180062fb7  lea     rax, [rbp+57h+var_70]
0x180062fbb  movups  [rbp+57h+var_40], xmm0
0x180062fbf  mov     rdx, rcx
0x180062fc2  movups  [rbp+57h+var_50], xmm1
0x180062fc6  nop     word ptr [rax+rax+00000000h]
0x180062fd0  mov     [rax], r15b
0x180062fd3  lea     rax, [rax+1]
0x180062fd7  sub     rdx, 1
0x180062fdb  jnz     short loc_180062FD0
0x180062fdd  xorps   xmm0, xmm0
0x180062fe0  mov     [rbp+57h+var_80+4], r15d
0x180062fe4  movups  xmmword ptr [rbp+57h+var_80], xmm0
0x180062fe8  lea     rax, [rbp+57h+var_50]
0x180062fec  nop     dword ptr [rax+00h]
0x180062ff0  mov     [rax], r15b
0x180062ff3  lea     rax, [rax+1]
0x180062ff7  sub     rcx, 1
0x180062ffb  jnz     short loc_180062FF0
0x180062ffd  lea     rdx, [rbp+57h+var_80]
0x180063001  mov     ecx, 1
0x180063006  call    cs:__imp_EtwEventActivityIdControl
0x18006300c  test    eax, eax
0x18006300e  jle     short loc_18006301A
0x180063010  movzx   eax, ax
0x180063013  or      eax, 80070000h
0x180063018  test    eax, eax
0x18006301a  js      loc_180063166
0x180063020  movaps  xmm0, xmmword ptr [rbp+57h+var_80]
0x180063024  movdqa  [rbp+57h+var_50], xmm0
0x180063029  lea     rdx, ?WinHttpEtwNullActivityId@@3U_GUID@@B; _GUID const WinHttpEtwNullActivityId
0x180063030  mov     [rbp+57h+var_80+4], r15d
0x180063034  mov     ecx, 2
0x180063039  call    cs:__imp_EtwEventActivityIdControl
0x18006303f  test    eax, eax
0x180063041  jle     short loc_18006304D
0x180063043  movzx   eax, ax
0x180063046  or      eax, 80070000h
0x18006304b  test    eax, eax
0x18006304d  js      loc_180063172
0x180063053  movaps  xmm0, [rbp+57h+var_50]
0x180063057  lea     r9, [rbp+57h+var_90]
0x18006305b  mov     rdx, [rsi+40h]
0x18006305f  mov     r8d, 20h ; ' '
0x180063065  mov     rcx, [r14+20h]
0x180063069  mov     rax, [rsi+30h]
0x18006306d  movups  [rbp+57h+var_70], xmm0
0x180063071  mov     [rbp+57h+var_60], 1
0x180063078  mov     [rsp+0C0h+var_A0], 4
0x180063080  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063085  cmp     [rbp+57h+var_60], r15d
0x180063089  jz      loc_180062F52
0x18006308f  lea     rdx, [rbp+57h+var_70]
0x180063093  mov     [rbp+57h+var_80+4], r15d
0x180063097  mov     ecx, 2
0x18006309c  call    cs:__imp_EtwEventActivityIdControl
0x1800630a2  test    eax, eax
0x1800630a4  jle     short loc_1800630B0
0x1800630a6  movzx   eax, ax
0x1800630a9  or      eax, 80070000h
0x1800630ae  test    eax, eax
0x1800630b0  jns     loc_180062F52
0x1800630b6  mov     [rbp+57h+var_80+4], 90h
0x1800630bd  jmp     loc_180062F52
0x1800630c2  mov     ebx, [rsi+2Ch]
0x1800630c5  call    cs:__imp_GetCurrentThreadId
0x1800630cb  cmp     eax, ebx
0x1800630cd  jz      loc_180062F91
0x1800630d3  mov     rcx, [rsi+48h]; hEvent
0x1800630d7  lea     rax, [rbp+57h+var_90]
0x1800630db  mov     [rsi+98h], rax
0x1800630e2  mov     dword ptr [rsi+8Ch], 1
0x1800630ec  mov     dword ptr [rsi+90h], 20h ; ' '
0x1800630f6  mov     dword ptr [rsi+0A0h], 4
0x180063100  call    cs:__imp_SetEvent
0x180063106  mov     rcx, [rsi+50h]; hHandle
0x18006310a  xor     r8d, r8d; bAlertable
0x18006310d  mov     edx, 0FFFFFFFFh; dwMilliseconds
0x180063112  call    cs:__imp_WaitForSingleObjectEx
0x180063118  mov     [rsi+8Ch], r15
0x18006311f  mov     [rsi+98h], r15
0x180063126  mov     [rsi+0A0h], r15d
0x18006312d  jmp     loc_180062F52
0x180063132  cmp     [rcx+29BCh], r15d
0x180063139  jz      loc_180062F52
0x18006313f  mov     rcx, [r8+80h]; this
0x180063146  lea     rdx, [rbp+57h+var_80]; int *
0x18006314a  call    ?GetHttp11DowngradeResendRequired@WEBIO_REQUEST@@QEAAKPEAH@Z; WEBIO_REQUEST::GetHttp11DowngradeResendRequired(int *)
0x18006314f  cmp     [rbp+57h+var_80], r15d
0x180063153  jz      loc_180062F52
0x180063159  mov     eax, [rsi+60h]
0x18006315c  mov     edi, r15d
0x18006315f  mov     [rbx], eax
0x180063161  jmp     loc_180062F4C
0x180063166  mov     [rbp+57h+var_80+4], 80h
0x18006316d  jmp     loc_180063029
0x180063172  mov     [rbp+57h+var_80+4], 90h
0x180063179  jmp     loc_180063053
```
