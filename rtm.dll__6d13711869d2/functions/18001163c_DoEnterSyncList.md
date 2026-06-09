# DoEnterSyncList

- ea: `0x18001163c`
- end: `0x180011770`
- name: `DoEnterSyncList`
- size: `308`
- prototype: ``
- caller_count: `21`
- callee_count: `1`
- tags: ``

## callers

- `0x18000dff4`
- `0x18000e200`
- `0x18000e260`
- `0x18000e4c0`
- `0x18000e7a0`
- `0x18000ea20`
- `0x18000ecec`
- `0x18000eea0`
- `0x18000f780`
- `0x18000fa20`
- `0x18000fcb0`
- `0x18000ff90`
- `0x180010090`
- `0x1800102d0`
- `0x1800106d0`
- `0x1800108f0`
- `0x180010ab0`
- `0x180010c60`
- `0x180010ef0`
- `0x180011270`
- `0x1800113e0`

## callees

- `0x18001163c`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x18001165a`
- `KERNEL32!EnterCriticalSection` at `0x18001172d`
- `KERNEL32!EnterCriticalSection` at `0x18001165a`
- `KERNEL32!EnterCriticalSection` at `0x18001172d`
- `KERNEL32!LeaveCriticalSection` at `0x1800116bf`
- `KERNEL32!LeaveCriticalSection` at `0x180011705`
- `KERNEL32!LeaveCriticalSection` at `0x180011715`
- `KERNEL32!LeaveCriticalSection` at `0x18001175d`
- `KERNEL32!LeaveCriticalSection` at `0x1800116bf`
- `KERNEL32!LeaveCriticalSection` at `0x180011705`
- `KERNEL32!LeaveCriticalSection` at `0x180011715`
- `KERNEL32!LeaveCriticalSection` at `0x18001175d`
- `KERNEL32!GetLastError` at `0x1800116ee`
- `KERNEL32!GetLastError` at `0x1800116ee`
- `KERNEL32!GlobalFree` at `0x1800116fc`
- `KERNEL32!GlobalFree` at `0x1800116fc`
- `KERNEL32!SetLastError` at `0x1800116c9`
- `KERNEL32!SetLastError` at `0x1800116c9`
- `KERNEL32!GlobalAlloc` at `0x1800116ab`
- `KERNEL32!GlobalAlloc` at `0x1800116ab`
- `KERNEL32!CreateEventA` at `0x1800116e0`
- `KERNEL32!CreateEventA` at `0x1800116e0`
- `KERNEL32!WaitForSingleObject` at `0x180011724`
- `KERNEL32!WaitForSingleObject` at `0x180011724`

## pseudocode

```c
char __fastcall DoEnterSyncList(__int64 a1, __int64 a2, char a3)
{
  struct _RTL_CRITICAL_SECTION *v3; // rsi
  int v7; // eax
  char v8; // bl
  bool v9; // zf
  _QWORD *v10; // rcx
  _QWORD *v11; // r14
  DWORD v12; // ecx
  HANDLE EventA; // rax
  DWORD LastError; // eax
  DWORD v16; // ebx
  _QWORD *v17; // rcx

  v3 = (struct _RTL_CRITICAL_SECTION *)(a1 + 344);
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 344));
  v7 = *(_DWORD *)(a2 + 8);
  if ( v7 > 0 )
  {
    if ( !a3 )
    {
      v8 = 0;
      goto LABEL_16;
    }
    v9 = *(_QWORD *)a2 == 0;
    *(_DWORD *)(a2 + 8) = v7 + 1;
    if ( v9 )
    {
      v10 = *(_QWORD **)(a1 + 56);
      if ( v10 )
      {
        *(_QWORD *)(a1 + 56) = *v10;
        *(_QWORD *)a2 = v10 - 1;
        goto LABEL_13;
      }
      v11 = GlobalAlloc(0, 0x10u);
      if ( !v11 )
      {
        --*(_DWORD *)(a2 + 8);
        LeaveCriticalSection(v3);
        v12 = 8;
LABEL_9:
        SetLastError(v12);
        return 0;
      }
      EventA = CreateEventA(0, 0, 0, 0);
      *v11 = EventA;
      if ( !EventA )
      {
        LastError = GetLastError();
        --*(_DWORD *)(a2 + 8);
        v16 = LastError;
        GlobalFree(v11);
        LeaveCriticalSection(v3);
        v12 = v16;
        goto LABEL_9;
      }
      *(_QWORD *)a2 = v11;
    }
LABEL_13:
    LeaveCriticalSection(v3);
    WaitForSingleObject(**(HANDLE **)a2, 0xFFFFFFFF);
    EnterCriticalSection(v3);
    v8 = 1;
    if ( *(_DWORD *)(a2 + 8) == 1 )
    {
      v17 = (_QWORD *)(*(_QWORD *)a2 + 8LL);
      *v17 = *(_QWORD *)(a1 + 56);
      *(_QWORD *)(a1 + 56) = v17;
      *(_QWORD *)a2 = 0;
    }
    goto LABEL_16;
  }
  v8 = 1;
  *(_DWORD *)(a2 + 8) = 1;
LABEL_16:
  LeaveCriticalSection(v3);
  return v8;
}

```

## disassembly

```asm
0x18001163c  push    rbx
0x18001163e  push    rbp
0x18001163f  push    rsi
0x180011640  push    rdi
0x180011641  push    r14
0x180011643  sub     rsp, 20h
0x180011647  lea     rsi, [rcx+158h]
0x18001164e  mov     rbp, rcx
0x180011651  mov     rcx, rsi; lpCriticalSection
0x180011654  mov     bl, r8b
0x180011657  mov     rdi, rdx
0x18001165a  call    cs:__imp_EnterCriticalSection
0x180011660  mov     eax, [rdi+8]
0x180011663  test    eax, eax
0x180011665  jg      short loc_180011674
0x180011667  mov     ebx, 1
0x18001166c  mov     [rdi+8], ebx
0x18001166f  jmp     loc_18001175A
0x180011674  test    bl, bl
0x180011676  jz      loc_180011758
0x18001167c  inc     eax
0x18001167e  cmp     qword ptr [rdi], 0
0x180011682  mov     [rdi+8], eax
0x180011685  jnz     loc_180011712
0x18001168b  mov     rcx, [rbp+38h]
0x18001168f  test    rcx, rcx
0x180011692  jz      short loc_1800116A4
0x180011694  mov     rax, [rcx]
0x180011697  mov     [rbp+38h], rax
0x18001169b  lea     rax, [rcx-8]
0x18001169f  mov     [rdi], rax
0x1800116a2  jmp     short loc_180011712
0x1800116a4  mov     edx, 10h; dwBytes
0x1800116a9  xor     ecx, ecx; uFlags
0x1800116ab  call    cs:__imp_GlobalAlloc
0x1800116b1  mov     r14, rax
0x1800116b4  test    rax, rax
0x1800116b7  jnz     short loc_1800116D6
0x1800116b9  dec     dword ptr [rdi+8]
0x1800116bc  mov     rcx, rsi; lpCriticalSection
0x1800116bf  call    cs:__imp_LeaveCriticalSection
0x1800116c5  lea     ecx, [r14+8]; dwErrCode
0x1800116c9  call    cs:__imp_SetLastError
0x1800116cf  xor     al, al
0x1800116d1  jmp     loc_180011765
0x1800116d6  xor     r9d, r9d; lpName
0x1800116d9  xor     r8d, r8d; bInitialState
0x1800116dc  xor     edx, edx; bManualReset
0x1800116de  xor     ecx, ecx; lpEventAttributes
0x1800116e0  call    cs:__imp_CreateEventA
0x1800116e6  mov     [r14], rax
0x1800116e9  test    rax, rax
0x1800116ec  jnz     short loc_18001170F
0x1800116ee  call    cs:__imp_GetLastError
0x1800116f4  dec     dword ptr [rdi+8]
0x1800116f7  mov     rcx, r14; hMem
0x1800116fa  mov     ebx, eax
0x1800116fc  call    cs:__imp_GlobalFree
0x180011702  mov     rcx, rsi; lpCriticalSection
0x180011705  call    cs:__imp_LeaveCriticalSection
0x18001170b  mov     ecx, ebx
0x18001170d  jmp     short loc_1800116C9
0x18001170f  mov     [rdi], r14
0x180011712  mov     rcx, rsi; lpCriticalSection
0x180011715  call    cs:__imp_LeaveCriticalSection
0x18001171b  mov     rcx, [rdi]
0x18001171e  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180011721  mov     rcx, [rcx]; hHandle
0x180011724  call    cs:__imp_WaitForSingleObject
0x18001172a  mov     rcx, rsi; lpCriticalSection
0x18001172d  call    cs:__imp_EnterCriticalSection
0x180011733  mov     ebx, 1
0x180011738  cmp     [rdi+8], ebx
0x18001173b  jnz     short loc_18001175A
0x18001173d  mov     rcx, [rdi]
0x180011740  mov     rax, [rbp+38h]
0x180011744  add     rcx, 8
0x180011748  mov     [rcx], rax
0x18001174b  mov     [rbp+38h], rcx
0x18001174f  mov     qword ptr [rdi], 0
0x180011756  jmp     short loc_18001175A
0x180011758  xor     bl, bl
0x18001175a  mov     rcx, rsi; lpCriticalSection
0x18001175d  call    cs:__imp_LeaveCriticalSection
0x180011763  mov     al, bl
0x180011765  add     rsp, 20h
0x180011769  pop     r14
0x18001176b  pop     rdi
0x18001176c  pop     rsi
0x18001176d  pop     rbp
0x18001176e  pop     rbx
0x18001176f  retn
```
