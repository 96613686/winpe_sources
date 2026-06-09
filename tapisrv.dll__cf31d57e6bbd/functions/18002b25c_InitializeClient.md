# InitializeClient

- ea: `0x18002b25c`
- end: `0x18002b44a`
- name: `InitializeClient`
- size: `494`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180010750`
- `0x180023060`

## callees

- `0x180029d08`
- `0x18002b25c`
- `0x18003dc84`
- `0x180040010`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x18002b351`
- `KERNEL32!HeapAlloc` at `0x18002b3da`
- `KERNEL32!HeapAlloc` at `0x18002b351`
- `KERNEL32!HeapAlloc` at `0x18002b3da`
- `KERNEL32!LeaveCriticalSection` at `0x18002b325`
- `KERNEL32!LeaveCriticalSection` at `0x18002b42a`
- `KERNEL32!LeaveCriticalSection` at `0x18002b325`
- `KERNEL32!LeaveCriticalSection` at `0x18002b42a`
- `KERNEL32!EnterCriticalSection` at `0x18002b303`
- `KERNEL32!EnterCriticalSection` at `0x18002b3ff`
- `KERNEL32!EnterCriticalSection` at `0x18002b303`
- `KERNEL32!EnterCriticalSection` at `0x18002b3ff`

## string_xrefs

- `0x18002b2e4`: `GetDeviceAccess failed - error x%lx`
- `0x18002b412`: `pDllList->lCount is less than 0 - pDllList %p`

## pseudocode

```c
__int64 __fastcall InitializeClient(__int64 a1)
{
  LPVOID v2; // rdi
  int v3; // eax
  unsigned int v4; // ebx
  unsigned int DeviceAccess; // eax
  unsigned int v7; // edi
  _QWORD *v8; // rbx
  __int64 v9; // rbp
  _DWORD *v10; // rax
  _DWORD *v11; // r14
  int v12; // eax
  _DWORD *v13; // rax

  if ( (dword_180051900 & 2) == 0 || (*(_BYTE *)(a1 + 216) & 1) != 0 )
    return 0;
  v2 = qword_180051988;
  v3 = (*((__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, __int64))qword_180051988 + 4))(
         *(_QWORD *)(a1 + 48),
         *(_QWORD *)(a1 + 24),
         *(_QWORD *)(a1 + 40),
         a1 + 72);
  v4 = v3;
  if ( v3 )
  {
    TRACELogPrint(65538, "ClientInitialize internal failure - error %lu", v3);
    return v4;
  }
  else
  {
    DeviceAccess = GetDeviceAccess((__int64)v2, a1, *(_QWORD *)(a1 + 72));
    v7 = DeviceAccess;
    if ( DeviceAccess )
    {
      TRACELogPrint(65538, "GetDeviceAccess failed - error x%lx", DeviceAccess);
    }
    else
    {
      EnterCriticalSection(&gDllListCritSec);
      v8 = lpParameter;
      if ( lpParameter )
      {
        ++*(_DWORD *)lpParameter;
        v8 = lpParameter;
      }
      LeaveCriticalSection(&gDllListCritSec);
      if ( v8 )
      {
        v9 = v8[1];
        if ( v9 )
        {
          v10 = HeapAlloc(ghTapisrvHeap, 8u, 0x18u);
          v11 = v10;
          if ( v10 )
          {
            *(_QWORD *)(a1 + 64) = v10;
            while ( v9 )
            {
              v11[2] = *(_DWORD *)(v9 + 8);
              v11[3] = 1;
              v12 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _DWORD *))(v9 + 32))(
                      *(_QWORD *)(a1 + 48),
                      *(_QWORD *)(a1 + 24),
                      *(_QWORD *)(a1 + 40),
                      v11);
              if ( v12 )
              {
                TRACELogPrint(65538, "ClientInitialize failed for %ls, result x%lx", *(const wchar_t **)(v9 + 232), v12);
                v11[3] = 0;
              }
              v9 = *(_QWORD *)(v9 + 248);
              if ( v9 )
              {
                v13 = HeapAlloc(ghTapisrvHeap, 8u, 0x18u);
                *((_QWORD *)v11 + 2) = v13;
                if ( !v13 )
                  goto LABEL_21;
                v11 = v13;
              }
              v7 = 0;
            }
          }
          else
          {
LABEL_21:
            v7 = -2147483580;
          }
        }
      }
      EnterCriticalSection(&gDllListCritSec);
      if ( v8 )
      {
        if ( --*(_DWORD *)v8 < 0 )
          TRACELogPrint(262146, "pDllList->lCount is less than 0 - pDllList %p", v8);
      }
      LeaveCriticalSection(&gDllListCritSec);
    }
    return v7;
  }
}

```

## disassembly

```asm
0x18002b25c  mov     [rsp+arg_0], rbx
0x18002b261  mov     [rsp+arg_10], rbp
0x18002b266  push    rsi
0x18002b267  push    rdi
0x18002b268  push    r14
0x18002b26a  sub     rsp, 30h
0x18002b26e  test    byte ptr cs:dword_180051900, 2
0x18002b275  mov     rsi, rcx
0x18002b278  jz      loc_18002B435
0x18002b27e  test    byte ptr [rcx+0D8h], 1
0x18002b285  jnz     loc_18002B435
0x18002b28b  mov     rdi, cs:qword_180051988
0x18002b292  lea     r9, [rcx+48h]
0x18002b296  mov     r8, [rcx+28h]
0x18002b29a  mov     rdx, [rcx+18h]
0x18002b29e  mov     rcx, [rcx+30h]
0x18002b2a2  mov     rax, [rdi+20h]
0x18002b2a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b2ab  mov     ebx, eax
0x18002b2ad  test    eax, eax
0x18002b2af  jz      short loc_18002B2CC
0x18002b2b1  mov     r8d, eax
0x18002b2b4  lea     rdx, aClientinitiali_0; "ClientInitialize internal failure - err"...
0x18002b2bb  mov     ecx, 10002h
0x18002b2c0  call    TRACELogPrint
0x18002b2c5  mov     eax, ebx
0x18002b2c7  jmp     loc_18002B437
0x18002b2cc  mov     r8, [rsi+48h]
0x18002b2d0  mov     rdx, rsi
0x18002b2d3  mov     rcx, rdi
0x18002b2d6  call    GetDeviceAccess
0x18002b2db  mov     edi, eax
0x18002b2dd  test    eax, eax
0x18002b2df  jz      short loc_18002B2FC
0x18002b2e1  mov     r8d, eax
0x18002b2e4  lea     rdx, aGetdeviceacces_0; "GetDeviceAccess failed - error x%lx"
0x18002b2eb  mov     ecx, 10002h
0x18002b2f0  call    TRACELogPrint
0x18002b2f5  mov     eax, edi
0x18002b2f7  jmp     loc_18002B437
0x18002b2fc  lea     rcx, gDllListCritSec; lpCriticalSection
0x18002b303  call    cs:__imp_EnterCriticalSection
0x18002b309  mov     rbx, cs:lpParameter
0x18002b310  test    rbx, rbx
0x18002b313  jz      short loc_18002B31E
0x18002b315  inc     dword ptr [rbx]
0x18002b317  mov     rbx, cs:lpParameter
0x18002b31e  lea     rcx, gDllListCritSec; lpCriticalSection
0x18002b325  call    cs:__imp_LeaveCriticalSection
0x18002b32b  test    rbx, rbx
0x18002b32e  jz      loc_18002B3F8
0x18002b334  mov     rbp, [rbx+8]
0x18002b338  test    rbp, rbp
0x18002b33b  jz      loc_18002B3F8
0x18002b341  mov     rcx, cs:ghTapisrvHeap; hHeap
0x18002b348  mov     edx, 8; dwFlags
0x18002b34d  lea     r8d, [rdx+10h]; dwBytes
0x18002b351  call    cs:__imp_HeapAlloc
0x18002b357  mov     r14, rax
0x18002b35a  test    rax, rax
0x18002b35d  jz      loc_18002B3F3
0x18002b363  mov     [rsi+40h], rax
0x18002b367  test    rbp, rbp
0x18002b36a  jz      loc_18002B3F8
0x18002b370  mov     eax, [rbp+8]
0x18002b373  mov     r9, r14
0x18002b376  mov     [r14+8], eax
0x18002b37a  mov     dword ptr [r14+0Ch], 1
0x18002b382  mov     r8, [rsi+28h]
0x18002b386  mov     rdx, [rsi+18h]
0x18002b38a  mov     rcx, [rsi+30h]
0x18002b38e  mov     rax, [rbp+20h]
0x18002b392  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b397  test    eax, eax
0x18002b399  jz      short loc_18002B3BE
0x18002b39b  mov     r8, [rbp+0E8h]
0x18002b3a2  lea     rdx, aClientinitiali; "ClientInitialize failed for %ls, result"...
0x18002b3a9  mov     r9d, eax
0x18002b3ac  mov     ecx, 10002h
0x18002b3b1  call    TRACELogPrint
0x18002b3b6  mov     dword ptr [r14+0Ch], 0
0x18002b3be  mov     rbp, [rbp+0F8h]
0x18002b3c5  test    rbp, rbp
0x18002b3c8  jz      short loc_18002B3EC
0x18002b3ca  mov     rcx, cs:ghTapisrvHeap; hHeap
0x18002b3d1  mov     edx, 8; dwFlags
0x18002b3d6  lea     r8d, [rdx+10h]; dwBytes
0x18002b3da  call    cs:__imp_HeapAlloc
0x18002b3e0  mov     [r14+10h], rax
0x18002b3e4  test    rax, rax
0x18002b3e7  jz      short loc_18002B3F3
0x18002b3e9  mov     r14, rax
0x18002b3ec  xor     edi, edi
0x18002b3ee  jmp     loc_18002B367
0x18002b3f3  mov     edi, 80000044h
0x18002b3f8  lea     rcx, gDllListCritSec; lpCriticalSection
0x18002b3ff  call    cs:__imp_EnterCriticalSection
0x18002b405  test    rbx, rbx
0x18002b408  jz      short loc_18002B423
0x18002b40a  sub     dword ptr [rbx], 1
0x18002b40d  jns     short loc_18002B423
0x18002b40f  mov     r8, rbx
0x18002b412  lea     rdx, aPdlllistLcount; "pDllList->lCount is less than 0 - pDllL"...
0x18002b419  mov     ecx, 40002h
0x18002b41e  call    TRACELogPrint
0x18002b423  lea     rcx, gDllListCritSec; lpCriticalSection
0x18002b42a  call    cs:__imp_LeaveCriticalSection
0x18002b430  jmp     loc_18002B2F5
0x18002b435  xor     eax, eax
0x18002b437  mov     rbx, [rsp+48h+arg_0]
0x18002b43c  mov     rbp, [rsp+48h+arg_10]
0x18002b441  add     rsp, 30h
0x18002b445  pop     r14
0x18002b447  pop     rdi
0x18002b448  pop     rsi
0x18002b449  retn
```
