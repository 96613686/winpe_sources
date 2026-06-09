# TestWindowProcess

- ea: `0x1800107b0`
- end: `0x18001093d`
- name: `TestWindowProcess`
- size: `397`
- prototype: ``
- caller_count: `15`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000b620`
- `0x18000b7d8`
- `0x18000be40`
- `0x1800105c0`
- `0x180010610`
- `0x180010b70`
- `0x180012340`
- `0x180016320`
- `0x18004c1e0`
- `0x18004d430`
- `0x18004dce4`
- `0x1800551c0`
- `0x180059370`
- `0x180092460`
- `0x180092bb0`

## callees

- `0x18000d210`
- `0x1800107b0`

## import_xrefs

- `win32u!NtUserGetThreadState` at `0x180010929`
- `win32u!NtUserGetThreadState` at `0x180010929`
- `ntdll!RtlSetLastWin32Error` at `0x180010915`
- `ntdll!RtlSetLastWin32Error` at `0x180010915`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800108a1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800108a1`

## pseudocode

```c
__int64 __fastcall TestWindowProcess(_DWORD *a1)
{
  unsigned __int64 v2; // rdx
  __int64 v3; // rax
  PVOID v4; // rbx
  PVOID Win32ThreadInfo; // rax
  HWND v6; // rdi
  __int64 v7; // rdx
  char v8; // al
  __int64 v9; // rbx
  int UniqueProcess; // edx
  int UniqueThread; // ecx
  struct tagWND *v13; // rax

  v2 = (unsigned __int16)*a1;
  if ( v2 < *(_QWORD *)(gSharedInfo + 8)
    && (v3 = (unsigned int)(dword_1800C9380 * v2) + qword_1800C9378, *(_BYTE *)(v3 + 24))
    && v3 )
  {
    v4 = *(PVOID *)(v3 + 8);
  }
  else
  {
    v4 = 0;
  }
  if ( NtCurrentTeb()->Win32ThreadInfo || (Win32ThreadInfo = (PVOID)NtUserGetThreadState(14)) != 0 )
    Win32ThreadInfo = NtCurrentTeb()->Win32ThreadInfo;
  if ( v4 == Win32ThreadInfo )
    return 1;
  v6 = *(HWND *)a1;
  if ( (unsigned __int64)(unsigned __int16)v6 >= *(_QWORD *)(gpsi + 8)
    || (unsigned __int64)(unsigned __int16)v6 >= *(_QWORD *)(gSharedInfo + 8)
    || (v7 = qword_1800C9378 + dword_1800C9380 * (unsigned int)(unsigned __int16)v6, (v8 = *(_BYTE *)(v7 + 24)) == 0)
    || !v7
    || v8 != 1
    || (*(_BYTE *)(v7 + 25) & 1) != 0
    || (WORD1(v6) & 0x7FFF) != *(_WORD *)(v7 + 26) )
  {
LABEL_24:
    RtlSetLastWin32Error(0x578u);
    return 0;
  }
  v9 = *(_QWORD *)(v7 + 8);
  if ( !v9 )
    return 0;
  if ( v9 != GetCurrentThreadId() )
  {
    v13 = ValidateHwnd(v6);
    if ( v13 )
    {
      UniqueProcess = *((_DWORD *)v13 + 83);
      UniqueThread = *((_DWORD *)v13 + 82);
      return UniqueThread && UniqueProcess == LODWORD(NtCurrentTeb()->ClientId.UniqueProcess);
    }
    goto LABEL_24;
  }
  UniqueProcess = (int)NtCurrentTeb()->ClientId.UniqueProcess;
  UniqueThread = (int)NtCurrentTeb()->ClientId.UniqueThread;
  return UniqueThread && UniqueProcess == LODWORD(NtCurrentTeb()->ClientId.UniqueProcess);
}

```

## disassembly

```asm
0x1800107b0  mov     [rsp+arg_0], rbx
0x1800107b5  push    rdi
0x1800107b6  sub     rsp, 20h
0x1800107ba  mov     eax, [rcx]
0x1800107bc  mov     rdi, rcx
0x1800107bf  movzx   edx, ax
0x1800107c2  mov     rax, cs:gSharedInfo
0x1800107c9  cmp     rdx, [rax+8]
0x1800107cd  jnb     loc_18001091D
0x1800107d3  imul    edx, cs:dword_1800C9380
0x1800107da  mov     rax, cs:qword_1800C9378
0x1800107e1  add     rax, rdx
0x1800107e4  cmp     byte ptr [rax+18h], 0
0x1800107e8  jz      loc_18001091D
0x1800107ee  test    rax, rax
0x1800107f1  jz      loc_18001091D
0x1800107f7  mov     rbx, [rax+8]
0x1800107fb  mov     rax, gs:30h
0x180010804  cmp     qword ptr [rax+78h], 0
0x180010809  jz      loc_180010924
0x18001080f  mov     rax, gs:30h
0x180010818  mov     rax, [rax+78h]
0x18001081c  cmp     rbx, rax
0x18001081f  jz      loc_1800108E5
0x180010825  mov     rax, cs:gpsi
0x18001082c  mov     rdi, [rdi]
0x18001082f  movzx   ecx, di
0x180010832  cmp     rcx, [rax+8]
0x180010836  jnb     loc_180010910
0x18001083c  mov     rax, cs:gSharedInfo
0x180010843  cmp     rcx, [rax+8]
0x180010847  jnb     loc_180010910
0x18001084d  imul    ecx, cs:dword_1800C9380
0x180010854  mov     edx, ecx
0x180010856  add     rdx, cs:qword_1800C9378
0x18001085d  movzx   eax, byte ptr [rdx+18h]
0x180010861  test    al, al
0x180010863  jz      loc_180010910
0x180010869  test    rdx, rdx
0x18001086c  jz      loc_180010910
0x180010872  cmp     al, 1
0x180010874  jnz     loc_180010910
0x18001087a  test    [rdx+19h], al
0x18001087d  jnz     loc_180010910
0x180010883  mov     rax, rdi
0x180010886  mov     ecx, 7FFFh
0x18001088b  shr     rax, 10h
0x18001088f  and     ax, cx
0x180010892  cmp     ax, [rdx+1Ah]
0x180010896  jnz     short loc_180010910
0x180010898  mov     rbx, [rdx+8]
0x18001089c  test    rbx, rbx
0x18001089f  jz      short loc_1800108D8
0x1800108a1  call    cs:__imp_GetCurrentThreadId
0x1800108a7  mov     eax, eax
0x1800108a9  cmp     rbx, rax
0x1800108ac  jnz     short loc_1800108F5
0x1800108ae  mov     rax, gs:30h
0x1800108b7  mov     edx, [rax+40h]
0x1800108ba  mov     rax, gs:30h
0x1800108c3  mov     ecx, [rax+48h]
0x1800108c6  test    ecx, ecx
0x1800108c8  jz      short loc_1800108D8
0x1800108ca  mov     rax, gs:30h
0x1800108d3  cmp     edx, [rax+40h]
0x1800108d6  jz      short loc_1800108E5
0x1800108d8  xor     eax, eax
0x1800108da  mov     rbx, [rsp+28h+arg_0]
0x1800108df  add     rsp, 20h
0x1800108e3  pop     rdi
0x1800108e4  retn
0x1800108e5  mov     rbx, [rsp+28h+arg_0]
0x1800108ea  mov     eax, 1
0x1800108ef  add     rsp, 20h
0x1800108f3  pop     rdi
0x1800108f4  retn
0x1800108f5  mov     rcx, rdi; HWND
0x1800108f8  call    ?ValidateHwnd@@YAPEAUtagWND@@PEAUHWND__@@@Z; ValidateHwnd(HWND__ *)
0x1800108fd  test    rax, rax
0x180010900  jz      short loc_180010910
0x180010902  mov     edx, [rax+14Ch]
0x180010908  mov     ecx, [rax+148h]
0x18001090e  jmp     short loc_1800108C6
0x180010910  mov     ecx, 578h; LastError
0x180010915  call    cs:__imp_RtlSetLastWin32Error
0x18001091b  jmp     short loc_1800108D8
0x18001091d  xor     ebx, ebx
0x18001091f  jmp     loc_1800107FB
0x180010924  mov     ecx, 0Eh
0x180010929  call    cs:__imp_NtUserGetThreadState
0x18001092f  test    rax, rax
0x180010932  jnz     loc_18001080F
0x180010938  jmp     loc_18001081C
```
