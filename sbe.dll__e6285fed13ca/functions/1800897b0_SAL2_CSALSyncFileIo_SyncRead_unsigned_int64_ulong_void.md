# SAL2::CSALSyncFileIo::SyncRead(unsigned __int64,ulong,void *)

- ea: `0x1800897b0`
- end: `0x180089948`
- name: `?SyncRead@CSALSyncFileIo@SAL2@@UEAAJ_KKPEAX@Z`
- size: `408`
- prototype: `int(SAL2::CSALSyncFileIo *__hidden this, unsigned __int64, unsigned int, void *)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops`

## callees

- `0x1800627f0`
- `0x1800897b0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180089868`
- `KERNEL32!GetLastError` at `0x1800898a5`
- `KERNEL32!GetLastError` at `0x180089928`
- `KERNEL32!GetLastError` at `0x180089868`
- `KERNEL32!GetLastError` at `0x1800898a5`
- `KERNEL32!GetLastError` at `0x180089928`
- `KERNEL32!GetOverlappedResult` at `0x18008989b`
- `KERNEL32!GetOverlappedResult` at `0x18008991e`
- `KERNEL32!GetOverlappedResult` at `0x18008989b`
- `KERNEL32!GetOverlappedResult` at `0x18008991e`
- `KERNEL32!ReadFile` at `0x18008985a`
- `KERNEL32!ReadFile` at `0x18008985a`

## pseudocode

```c
__int64 __fastcall SAL2::CSALSyncFileIo::SyncRead(SAL2::CSALSyncFileIo *this, void *a2, DWORD a3, void *a4)
{
  void *v5; // rcx
  unsigned int v7; // ebx
  unsigned int v8; // r9d
  unsigned int v9; // r8d
  void *v10; // rax
  signed int v11; // eax
  signed int v12; // eax
  signed int LastError; // eax
  struct _OVERLAPPED Overlapped; // [rsp+30h] [rbp-28h] BYREF
  DWORD NumberOfBytesTransferred; // [rsp+80h] [rbp+28h] BYREF

  NumberOfBytesTransferred = 0;
  v5 = (void *)*((_QWORD *)this + 36);
  Overlapped.Internal = 0;
  Overlapped.InternalHigh = 0;
  if ( v5 == (void *)-1LL )
  {
    v7 = -2147418113;
    v8 = -2147418113;
    v9 = 1291;
LABEL_19:
    SBEBasicTracers::EtwTraceError(
      (SAL2::CSALSyncFileIo *)((char *)this + 112),
      "multimedia\\dshow\\filters\\sbe\\sal\\salfileio.cpp",
      v9,
      v8);
    return v7;
  }
  if ( !a3 )
  {
    v7 = -2147024809;
    v8 = -2147024809;
    v9 = 1292;
    goto LABEL_19;
  }
  if ( !a4 )
  {
    v7 = -2147024809;
    v8 = -2147024809;
    v9 = 1293;
    goto LABEL_19;
  }
  v10 = (void *)*((_QWORD *)this + 38);
  Overlapped.Pointer = a2;
  Overlapped.hEvent = v10;
  if ( ReadFile(v5, a4, a3, 0, &Overlapped) )
  {
    v7 = 0;
    if ( !GetOverlappedResult(*((HANDLE *)this + 36), &Overlapped, &NumberOfBytesTransferred, 1) )
    {
      LastError = GetLastError();
      v7 = LastError;
      if ( LastError > 0 )
        v7 = (unsigned __int16)LastError | 0x80070000;
      v8 = v7;
      v9 = 1326;
      goto LABEL_19;
    }
  }
  else
  {
    v11 = GetLastError();
    if ( v11 > 0 )
      v7 = (unsigned __int16)v11 | 0x80070000;
    else
      v7 = v11;
    if ( v11 == 997 )
    {
      if ( !GetOverlappedResult(*((HANDLE *)this + 36), &Overlapped, &NumberOfBytesTransferred, 1) )
      {
        v12 = GetLastError();
        v7 = v12;
        if ( v12 > 0 )
          v7 = (unsigned __int16)v12 | 0x80070000;
        v8 = v7;
        v9 = 1316;
        goto LABEL_19;
      }
      v7 = 0;
    }
    else if ( (v7 & 0x80000000) != 0 )
    {
      v8 = v7;
      v9 = 1320;
      goto LABEL_19;
    }
  }
  if ( NumberOfBytesTransferred < a3 )
  {
    v7 = -2147024774;
    v8 = -2147024774;
    v9 = 1332;
    goto LABEL_19;
  }
  return v7;
}

```

## disassembly

```asm
0x1800897b0  push    rbp
0x1800897b2  push    rbx
0x1800897b3  push    rdi
0x1800897b4  push    r14
0x1800897b6  mov     rbp, rsp
0x1800897b9  sub     rsp, 58h
0x1800897bd  mov     rdi, rcx
0x1800897c0  mov     [rbp+NumberOfBytesTransferred], 0
0x1800897c7  mov     rcx, [rcx+120h]; hFile
0x1800897ce  mov     r10, r9
0x1800897d1  mov     [rbp+Overlapped.Internal], 0
0x1800897d9  mov     r14d, r8d
0x1800897dc  mov     [rbp+Overlapped.InternalHigh], 0
0x1800897e4  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800897e8  jnz     short loc_180089800
0x1800897ea  mov     ebx, 8000FFFFh
0x1800897ef  mov     r9d, 8000FFFFh
0x1800897f5  mov     r8d, 50Bh
0x1800897fb  jmp     loc_1800898DE
0x180089800  test    r14d, r14d
0x180089803  jnz     short loc_18008981B
0x180089805  mov     ebx, 80070057h
0x18008980a  mov     r9d, 80070057h
0x180089810  mov     r8d, 50Ch
0x180089816  jmp     loc_1800898DE
0x18008981b  test    r10, r10
0x18008981e  jnz     short loc_180089836
0x180089820  mov     ebx, 80070057h
0x180089825  mov     r9d, 80070057h
0x18008982b  mov     r8d, 50Dh; nNumberOfBytesToRead
0x180089831  jmp     loc_1800898DE
0x180089836  mov     rax, [rdi+130h]
0x18008983d  xor     r9d, r9d; lpNumberOfBytesRead
0x180089840  mov     dword ptr [rbp+Overlapped.10h], edx
0x180089843  shr     rdx, 20h
0x180089847  mov     [rbp+Overlapped.hEvent], rax
0x18008984b  lea     rax, [rbp+Overlapped]
0x18008984f  mov     dword ptr [rbp+Overlapped.10h+4], edx
0x180089852  mov     rdx, r10; lpBuffer
0x180089855  mov     [rsp+58h+lpOverlapped], rax; lpOverlapped
0x18008985a  call    cs:__imp_ReadFile
0x180089860  test    eax, eax
0x180089862  jnz     loc_180089909
0x180089868  call    cs:__imp_GetLastError
0x18008986e  test    eax, eax
0x180089870  jg      short loc_180089876
0x180089872  mov     ebx, eax
0x180089874  jmp     short loc_18008987F
0x180089876  movzx   ebx, ax
0x180089879  or      ebx, 80070000h
0x18008987f  cmp     eax, 3E5h
0x180089884  jnz     short loc_1800898FA
0x180089886  mov     rcx, [rdi+120h]; hFile
0x18008988d  lea     r8, [rbp+NumberOfBytesTransferred]; lpNumberOfBytesTransferred
0x180089891  mov     r9d, 1; bWait
0x180089897  lea     rdx, [rbp+Overlapped]; lpOverlapped
0x18008989b  call    cs:__imp_GetOverlappedResult
0x1800898a1  test    eax, eax
0x1800898a3  jnz     short loc_1800898C5
0x1800898a5  call    cs:__imp_GetLastError
0x1800898ab  mov     ebx, eax
0x1800898ad  test    eax, eax
0x1800898af  jle     short loc_1800898BA
0x1800898b1  movzx   ebx, ax
0x1800898b4  or      ebx, 80070000h
0x1800898ba  mov     r9d, ebx
0x1800898bd  mov     r8d, 524h
0x1800898c3  jmp     short loc_1800898DE
0x1800898c5  xor     ebx, ebx
0x1800898c7  cmp     [rbp+NumberOfBytesTransferred], r14d
0x1800898cb  jnb     short loc_1800898EE
0x1800898cd  mov     ebx, 8007007Ah
0x1800898d2  mov     r9d, 8007007Ah; unsigned int
0x1800898d8  mov     r8d, 534h; unsigned int
0x1800898de  lea     rdx, aMultimediaDsho_11; "multimedia\\dshow\\filters\\sbe\\sal\\s"...
0x1800898e5  lea     rcx, [rdi+70h]; struct CEhEventTracer *
0x1800898e9  call    ?EtwTraceError@SBEBasicTracers@@SAXAEAVCEhEventTracer@@PEBDKK@Z; SBEBasicTracers::EtwTraceError(CEhEventTracer &,char const *,ulong,ulong)
0x1800898ee  mov     eax, ebx
0x1800898f0  add     rsp, 58h
0x1800898f4  pop     r14
0x1800898f6  pop     rdi
0x1800898f7  pop     rbx
0x1800898f8  pop     rbp
0x1800898f9  retn
0x1800898fa  test    ebx, ebx
0x1800898fc  jns     short loc_1800898C7
0x1800898fe  mov     r9d, ebx
0x180089901  mov     r8d, 528h
0x180089907  jmp     short loc_1800898DE
0x180089909  mov     rcx, [rdi+120h]; hFile
0x180089910  lea     r8, [rbp+NumberOfBytesTransferred]; lpNumberOfBytesTransferred
0x180089914  xor     ebx, ebx
0x180089916  lea     rdx, [rbp+Overlapped]; lpOverlapped
0x18008991a  lea     r9d, [rbx+1]; bWait
0x18008991e  call    cs:__imp_GetOverlappedResult
0x180089924  test    eax, eax
0x180089926  jnz     short loc_1800898C7
0x180089928  call    cs:__imp_GetLastError
0x18008992e  mov     ebx, eax
0x180089930  test    eax, eax
0x180089932  jle     short loc_18008993D
0x180089934  movzx   ebx, ax
0x180089937  or      ebx, 80070000h
0x18008993d  mov     r9d, ebx
0x180089940  mov     r8d, 52Eh
0x180089946  jmp     short loc_1800898DE
```
