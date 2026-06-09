# CWinInetHelperClass::ExecuteConnectionThread(int,WHCConnectionErrors *,long *,ulong *,_WINHTTP_PROXY_INFO * const,sockaddr_storage *)

- ea: `0x18000f91c`
- end: `0x18000fce0`
- name: `?ExecuteConnectionThread@CWinInetHelperClass@@AEAAJHPEAW4WHCConnectionErrors@@PEAJPEAKQEAU_WINHTTP_PROXY_INFO@@PEAUsockaddr_storage@@@Z`
- size: `964`
- prototype: `__int64 __fastcall(CWinInetHelperClass *__hidden this, int, enum WHCConnectionErrors *, int *, unsigned int *, struct _WINHTTP_PROXY_INFO *const, struct sockaddr_storage *)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x18000929c`
- `0x18000d160`

## callees

- `0x18000f91c`
- `0x18001000c`
- `0x180010174`
- `0x180014010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000fb4b`
- `KERNEL32!GetLastError` at `0x18000fb4b`
- `KERNEL32!CloseHandle` at `0x18000fa09`
- `KERNEL32!CloseHandle` at `0x18000fc59`
- `KERNEL32!CloseHandle` at `0x18000fa09`
- `KERNEL32!CloseHandle` at `0x18000fc59`
- `KERNEL32!WaitForSingleObjectEx` at `0x18000f99f`
- `KERNEL32!WaitForSingleObjectEx` at `0x18000fbe0`
- `KERNEL32!WaitForSingleObjectEx` at `0x18000f99f`
- `KERNEL32!WaitForSingleObjectEx` at `0x18000fbe0`
- `KERNEL32!GetCurrentThread` at `0x18000fb20`
- `KERNEL32!GetCurrentThread` at `0x18000fb20`
- `KERNEL32!CreateThread` at `0x18000fba9`
- `KERNEL32!CreateThread` at `0x18000fba9`
- `ADVAPI32!OpenThreadToken` at `0x18000fb3b`
- `ADVAPI32!OpenThreadToken` at `0x18000fb3b`

## string_xrefs

- `0x18000fc9c`: `We've reached the maximum number of connection threads allowed, proceeding as if we timed out.`

## pseudocode

```c
__int64 __fastcall CWinInetHelperClass::ExecuteConnectionThread(
        CWinInetHelperClass *this,
        int a2,
        enum WHCConnectionErrors *a3,
        int *a4,
        unsigned int *a5,
        struct _WINHTTP_PROXY_INFO *const a6,
        struct sockaddr_storage *a7)
{
  signed int v11; // ebx
  unsigned __int64 v12; // r14
  void *v13; // rcx
  DWORD v14; // eax
  void *v15; // rcx
  __int64 v16; // rax
  __int64 v17; // r15
  HANDLE CurrentThread; // rax
  signed int LastError; // eax
  HANDLE Thread; // rax
  DWORD v21; // eax
  void *v22; // rcx
  __int64 v23; // rcx
  char *lpParameter; // [rsp+30h] [rbp-38h]

  if ( !a3 || !a4 || !a5 || !a6 )
    return 2147942487LL;
  v11 = 0;
  v12 = (-(__int64)(a2 != 0) & 0xFFFFFFFFFFFFFFF8uLL) + 4432;
  v13 = *(void **)((char *)this + v12);
  if ( v13 )
  {
    v14 = WaitForSingleObjectEx(v13, 0x1388u, 0);
    *a5 = *(_DWORD *)((char *)this + (-(__int64)(a2 != 0) & 0xFFFFFFFFFFFFFFA8uLL) + 4580);
    if ( v14 == 258 )
    {
      *(_DWORD *)a3 = 2;
      *a4 = 0;
    }
    else
    {
      *(_DWORD *)a3 = *(_DWORD *)((char *)this + (-(__int64)(a2 != 0) & 0xFFFFFFFFFFFFFFA8uLL) + 4576);
      v15 = *(void **)((char *)this + v12);
      *a4 = *(_DWORD *)((char *)this + (-(__int64)(a2 != 0) & 0xFFFFFFFFFFFFFFA8uLL) + 4572);
      CloseHandle(v15);
      *(_QWORD *)((char *)this + v12) = 0;
      v16 = a2 == 0 ? 4 : 0;
      if ( *(int *)((char *)qword_18001BDC8 + v16) >= 0 )
        _InterlockedDecrement((volatile signed __int32 *)((char *)qword_18001BDC8 + v16));
    }
  }
  else
  {
    v17 = a2 == 0 ? 4 : 0;
    if ( *(int *)((char *)qword_18001BDC8 + v17) >= 2 )
    {
      *a4 = 0;
      *(_DWORD *)a3 = 2;
      v23 = *((_QWORD *)this + 602);
      if ( v23 )
        (*(void (__fastcall **)(__int64, __int64, _QWORD, const wchar_t *, const wchar_t *))(*(_QWORD *)v23 + 24LL))(
          v23,
          2,
          0,
          L"WinInetHelperClass",
          L"We've reached the maximum number of connection threads allowed, proceeding as if we timed out.");
    }
    else
    {
      _InterlockedIncrement((volatile signed __int32 *)((char *)qword_18001BDC8 + v17));
      lpParameter = (char *)this + (-(__int64)(a2 != 0) & 0xFFFFFFFFFFFFFFA8uLL) + 4544;
      *(_QWORD *)lpParameter = (char *)this + 1152;
      *(_QWORD *)((char *)this + (-(__int64)(a2 != 0) & 0xFFFFFFFFFFFFFFA8uLL) + 4552) = (char *)this + 120;
      *(_WORD *)((char *)this + (-(__int64)(a2 != 0) & 0xFFFFFFFFFFFFFFA8uLL) + 4564) = *((_WORD *)this + 572);
      *(_DWORD *)((char *)this + (-(__int64)(a2 != 0) & 0xFFFFFFFFFFFFFFA8uLL) + 4560) = *((_DWORD *)this + 287);
      *(_DWORD *)((char *)this + (-(__int64)(a2 != 0) & 0xFFFFFFFFFFFFFFA8uLL) + 4568) = *((_DWORD *)this + 1202);
      *(_QWORD *)((char *)this + (-(__int64)(a2 != 0) & 0xFFFFFFFFFFFFFFA8uLL) + 4584) = a6;
      *(_QWORD *)((char *)this + (-(__int64)(a2 != 0) & 0xFFFFFFFFFFFFFFA8uLL) + 4608) = a7;
      *((_QWORD *)lpParameter + 10) = 0;
      CurrentThread = GetCurrentThread();
      if ( OpenThreadToken(CurrentThread, 0xCu, 1, (PHANDLE)lpParameter + 10)
        || (LastError = GetLastError(), v11 = LastError, LastError == 1008) )
      {
        v11 = 0;
      }
      else if ( LastError > 0 )
      {
        v11 = (unsigned __int16)LastError | 0x80070000;
      }
      if ( v11 >= 0 )
      {
        NetTraceMarkContextActivityStart(lpParameter, 1u);
        Thread = CreateThread(0, 0, ConnectionThread, lpParameter, 0, 0);
        *(_QWORD *)((char *)this + v12) = Thread;
        if ( Thread )
        {
          v21 = WaitForSingleObjectEx(Thread, 0x8CA0u, 0);
          *a5 = *(_DWORD *)((char *)this + (-(__int64)(a2 != 0) & 0xFFFFFFFFFFFFFFA8uLL) + 4580);
          if ( v21 == 258 )
          {
            *(_DWORD *)a3 = 2;
            *a4 = 0;
          }
          else
          {
            *(_DWORD *)a3 = *(_DWORD *)((char *)this + (-(__int64)(a2 != 0) & 0xFFFFFFFFFFFFFFA8uLL) + 4576);
            v22 = *(void **)((char *)this + v12);
            *a4 = *(_DWORD *)((char *)this + (-(__int64)(a2 != 0) & 0xFFFFFFFFFFFFFFA8uLL) + 4572);
            CloseHandle(v22);
            *(_QWORD *)((char *)this + v12) = 0;
            if ( *(int *)((char *)qword_18001BDC8 + v17) >= 0 )
              _InterlockedDecrement((volatile signed __int32 *)((char *)qword_18001BDC8 + v17));
          }
        }
        else
        {
          NetTraceMarkContextActivityStop(lpParameter, 1u);
          return (unsigned int)-2147023842;
        }
      }
    }
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18000f91c  mov     [rsp+arg_0], rbx
0x18000f921  mov     [rsp+arg_8], rbp
0x18000f926  mov     [rsp+arg_10], r8
0x18000f92b  push    rsi
0x18000f92c  push    rdi
0x18000f92d  push    r13
0x18000f92f  push    r14
0x18000f931  push    r15
0x18000f933  sub     rsp, 40h
0x18000f937  mov     r13, r9
0x18000f93a  mov     r15, r8
0x18000f93d  mov     esi, edx
0x18000f93f  mov     rdi, rcx
0x18000f942  test    r8, r8
0x18000f945  jz      loc_18000FCC3
0x18000f94b  test    r9, r9
0x18000f94e  jz      loc_18000FCC3
0x18000f954  mov     rbp, [rsp+68h+arg_20]
0x18000f95c  test    rbp, rbp
0x18000f95f  jz      loc_18000FCC3
0x18000f965  mov     r9, [rsp+68h+arg_28]
0x18000f96d  test    r9, r9
0x18000f970  jz      loc_18000FCC3
0x18000f976  xor     ebx, ebx
0x18000f978  mov     eax, edx
0x18000f97a  neg     eax
0x18000f97c  sbb     r14, r14
0x18000f97f  and     r14, 0FFFFFFFFFFFFFFF8h
0x18000f983  add     r14, 1150h
0x18000f98a  mov     rcx, [r14+rcx]; hHandle
0x18000f98e  test    rcx, rcx
0x18000f991  jz      loc_18000FA3D
0x18000f997  xor     r8d, r8d; bAlertable
0x18000f99a  mov     edx, 1388h; dwMilliseconds
0x18000f99f  call    cs:__imp_WaitForSingleObjectEx
0x18000f9a6  nop     dword ptr [rax+rax+00h]
0x18000f9ab  mov     ecx, eax
0x18000f9ad  mov     eax, esi
0x18000f9af  neg     eax
0x18000f9b1  sbb     rax, rax
0x18000f9b4  and     rax, 0FFFFFFFFFFFFFFA8h
0x18000f9b8  mov     eax, [rax+rdi+11E4h]
0x18000f9bf  mov     [rbp+0], eax
0x18000f9c2  cmp     ecx, 102h
0x18000f9c8  jnz     short loc_18000F9DA
0x18000f9ca  mov     dword ptr [r15], 2
0x18000f9d1  mov     [r13+0], ebx
0x18000f9d5  jmp     loc_18000FCBF
0x18000f9da  mov     eax, esi
0x18000f9dc  neg     eax
0x18000f9de  sbb     rax, rax
0x18000f9e1  and     rax, 0FFFFFFFFFFFFFFA8h
0x18000f9e5  mov     eax, [rax+rdi+11E0h]
0x18000f9ec  mov     [r15], eax
0x18000f9ef  mov     eax, esi
0x18000f9f1  mov     rcx, [r14+rdi]; hObject
0x18000f9f5  neg     eax
0x18000f9f7  sbb     rax, rax
0x18000f9fa  and     rax, 0FFFFFFFFFFFFFFA8h
0x18000f9fe  mov     eax, [rax+rdi+11DCh]
0x18000fa05  mov     [r13+0], eax
0x18000fa09  call    cs:__imp_CloseHandle
0x18000fa10  nop     dword ptr [rax+rax+00h]
0x18000fa15  neg     esi
0x18000fa17  mov     [r14+rdi], rbx
0x18000fa1b  lea     rbp, qword_18001BDC8
0x18000fa22  sbb     rax, rax
0x18000fa25  not     rax
0x18000fa28  and     eax, 4
0x18000fa2b  cmp     [rax+rbp], ebx
0x18000fa2e  jl      loc_18000FCBF
0x18000fa34  lock dec dword ptr [rax+rbp]
0x18000fa38  jmp     loc_18000FCBF
0x18000fa3d  mov     eax, esi
0x18000fa3f  lea     rbp, qword_18001BDC8
0x18000fa46  neg     eax
0x18000fa48  sbb     r15, r15
0x18000fa4b  not     r15
0x18000fa4e  and     r15d, 4
0x18000fa52  cmp     dword ptr [r15+rbp], 2
0x18000fa57  jge     loc_18000FC7B
0x18000fa5d  lock inc dword ptr [r15+rbp]
0x18000fa62  mov     eax, esi
0x18000fa64  lea     rdx, [rdi+78h]
0x18000fa68  neg     eax
0x18000fa6a  lea     r8, [rdi+11C0h]
0x18000fa71  lea     rax, [rdi+480h]
0x18000fa78  sbb     rcx, rcx
0x18000fa7b  and     rcx, 0FFFFFFFFFFFFFFA8h
0x18000fa7f  add     r8, rcx
0x18000fa82  mov     [rsp+68h+lpParameter], r8
0x18000fa87  mov     [r8], rax
0x18000fa8a  lea     rbx, [r8+50h]
0x18000fa8e  mov     eax, esi
0x18000fa90  neg     eax
0x18000fa92  mov     eax, esi
0x18000fa94  sbb     rcx, rcx
0x18000fa97  and     rcx, 0FFFFFFFFFFFFFFA8h
0x18000fa9b  neg     eax
0x18000fa9d  mov     [rcx+rdi+11C8h], rdx
0x18000faa5  sbb     rcx, rcx
0x18000faa8  movzx   eax, word ptr [rdi+478h]
0x18000faaf  and     rcx, 0FFFFFFFFFFFFFFA8h
0x18000fab3  mov     [rcx+rdi+11D4h], ax
0x18000fabb  mov     eax, esi
0x18000fabd  neg     eax
0x18000fabf  mov     eax, [rdi+47Ch]
0x18000fac5  sbb     rcx, rcx
0x18000fac8  and     rcx, 0FFFFFFFFFFFFFFA8h
0x18000facc  mov     [rcx+rdi+11D0h], eax
0x18000fad3  mov     eax, esi
0x18000fad5  neg     eax
0x18000fad7  mov     eax, [rdi+12C8h]
0x18000fadd  sbb     rcx, rcx
0x18000fae0  and     rcx, 0FFFFFFFFFFFFFFA8h
0x18000fae4  mov     [rcx+rdi+11D8h], eax
0x18000faeb  mov     eax, esi
0x18000faed  neg     eax
0x18000faef  mov     eax, esi
0x18000faf1  sbb     rcx, rcx
0x18000faf4  and     rcx, 0FFFFFFFFFFFFFFA8h
0x18000faf8  neg     eax
0x18000fafa  mov     rax, [rsp+68h+arg_30]
0x18000fb02  mov     [rcx+rdi+11E8h], r9
0x18000fb0a  sbb     rcx, rcx
0x18000fb0d  and     rcx, 0FFFFFFFFFFFFFFA8h
0x18000fb11  mov     [rcx+rdi+1200h], rax
0x18000fb19  mov     qword ptr [rbx], 0
0x18000fb20  call    cs:__imp_GetCurrentThread
0x18000fb27  nop     dword ptr [rax+rax+00h]
0x18000fb2c  mov     edx, 0Ch; DesiredAccess
0x18000fb31  mov     r9, rbx; TokenHandle
0x18000fb34  mov     rcx, rax; ThreadHandle
0x18000fb37  lea     r8d, [rdx-0Bh]; OpenAsSelf
0x18000fb3b  call    cs:__imp_OpenThreadToken
0x18000fb42  nop     dword ptr [rax+rax+00h]
0x18000fb47  test    eax, eax
0x18000fb49  jnz     short loc_18000FB6F
0x18000fb4b  call    cs:__imp_GetLastError
0x18000fb52  nop     dword ptr [rax+rax+00h]
0x18000fb57  mov     ebx, eax
0x18000fb59  cmp     eax, 3F0h
0x18000fb5e  jz      short loc_18000FB6F
0x18000fb60  test    eax, eax
0x18000fb62  jle     short loc_18000FB71
0x18000fb64  movzx   ebx, ax
0x18000fb67  or      ebx, 80070000h
0x18000fb6d  jmp     short loc_18000FB71
0x18000fb6f  xor     ebx, ebx
0x18000fb71  test    ebx, ebx
0x18000fb73  js      loc_18000FCBF
0x18000fb79  mov     rcx, [rsp+68h+lpParameter]; void *
0x18000fb7e  mov     edx, 1; unsigned int
0x18000fb83  call    ?NetTraceMarkContextActivityStart@@YAXPEAXI@Z; NetTraceMarkContextActivityStart(void *,uint)
0x18000fb88  mov     r9, [rsp+68h+lpParameter]; lpParameter
0x18000fb8d  lea     r8, ?ConnectionThread@@YAKPEAX@Z; lpStartAddress
0x18000fb94  xor     edx, edx; dwStackSize
0x18000fb96  mov     [rsp+68h+lpThreadId], 0; lpThreadId
0x18000fb9f  xor     ecx, ecx; lpThreadAttributes
0x18000fba1  mov     [rsp+68h+dwCreationFlags], 0; dwCreationFlags
0x18000fba9  call    cs:__imp_CreateThread
0x18000fbb0  nop     dword ptr [rax+rax+00h]
0x18000fbb5  mov     [r14+rdi], rax
0x18000fbb9  test    rax, rax
0x18000fbbc  jnz     short loc_18000FBD5
0x18000fbbe  mov     rcx, [rsp+68h+lpParameter]; void *
0x18000fbc3  lea     edx, [rax+1]; unsigned int
0x18000fbc6  call    ?NetTraceMarkContextActivityStop@@YAXPEAXI@Z; NetTraceMarkContextActivityStop(void *,uint)
0x18000fbcb  mov     ebx, 8007041Eh
0x18000fbd0  jmp     loc_18000FCBF
0x18000fbd5  xor     r8d, r8d; bAlertable
0x18000fbd8  mov     edx, 8CA0h; dwMilliseconds
0x18000fbdd  mov     rcx, rax; hHandle
0x18000fbe0  call    cs:__imp_WaitForSingleObjectEx
0x18000fbe7  nop     dword ptr [rax+rax+00h]
0x18000fbec  mov     rdx, [rsp+68h+arg_20]
0x18000fbf4  mov     ecx, eax
0x18000fbf6  mov     eax, esi
0x18000fbf8  neg     eax
0x18000fbfa  sbb     rax, rax
0x18000fbfd  and     rax, 0FFFFFFFFFFFFFFA8h
0x18000fc01  cmp     ecx, 102h
0x18000fc07  mov     rcx, [rsp+68h+arg_10]
0x18000fc0f  mov     eax, [rax+rdi+11E4h]
0x18000fc16  mov     [rdx], eax
0x18000fc18  jnz     short loc_18000FC2D
0x18000fc1a  mov     dword ptr [rcx], 2
0x18000fc20  mov     dword ptr [r13+0], 0
0x18000fc28  jmp     loc_18000FCBF
0x18000fc2d  mov     eax, esi
0x18000fc2f  neg     eax
0x18000fc31  sbb     rax, rax
0x18000fc34  and     rax, 0FFFFFFFFFFFFFFA8h
0x18000fc38  neg     esi
0x18000fc3a  mov     eax, [rax+rdi+11E0h]
0x18000fc41  mov     [rcx], eax
0x18000fc43  sbb     rax, rax
0x18000fc46  mov     rcx, [r14+rdi]; hObject
0x18000fc4a  and     rax, 0FFFFFFFFFFFFFFA8h
0x18000fc4e  mov     eax, [rax+rdi+11DCh]
0x18000fc55  mov     [r13+0], eax
0x18000fc59  call    cs:__imp_CloseHandle
0x18000fc60  nop     dword ptr [rax+rax+00h]
0x18000fc65  mov     qword ptr [r14+rdi], 0
0x18000fc6d  cmp     dword ptr [r15+rbp], 0
0x18000fc72  jl      short loc_18000FCBF
0x18000fc74  lock dec dword ptr [r15+rbp]
0x18000fc79  jmp     short loc_18000FCBF
0x18000fc7b  mov     rcx, [rsp+68h+arg_10]
0x18000fc83  mov     [r13+0], ebx
0x18000fc87  mov     dword ptr [rcx], 2
0x18000fc8d  mov     rcx, [rdi+12D0h]
0x18000fc94  test    rcx, rcx
0x18000fc97  jz      short loc_18000FCBF
0x18000fc99  mov     r9, [rcx]
0x18000fc9c  lea     rdx, aWeVeReachedThe; "We've reached the maximum number of con"...
0x18000fca3  xor     r8d, r8d
0x18000fca6  mov     qword ptr [rsp+68h+dwCreationFlags], rdx
0x18000fcab  mov     rax, [r9+18h]
0x18000fcaf  lea     r9, aWininethelperc; "WinInetHelperClass"
0x18000fcb6  lea     edx, [r8+2]
0x18000fcba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fcbf  mov     eax, ebx
0x18000fcc1  jmp     short loc_18000FCC8
0x18000fcc3  mov     eax, 80070057h
0x18000fcc8  mov     rbx, [rsp+68h+arg_0]
0x18000fccd  mov     rbp, [rsp+68h+arg_8]
0x18000fcd2  add     rsp, 40h
0x18000fcd6  pop     r15
0x18000fcd8  pop     r14
0x18000fcda  pop     r13
0x18000fcdc  pop     rdi
0x18000fcdd  pop     rsi
0x18000fcde  retn
```
