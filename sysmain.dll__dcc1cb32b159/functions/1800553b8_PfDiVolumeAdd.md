# PfDiVolumeAdd

- ea: `0x1800553b8`
- end: `0x180055663`
- name: `PfDiVolumeAdd`
- size: `683`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops, service_task`

## callers

- `0x180055010`
- `0x180055234`

## callees

- `0x180007a64`
- `0x180007c78`
- `0x180007cbc`
- `0x180011f34`
- `0x18003a2ac`
- `0x1800553b8`
- `0x18005af4c`
- `0x18007354c`
- `0x180080f8c`
- `0x1800b64c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005544f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005544f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180055627`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180055627`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18005543d`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18005543d`
- `api-ms-win-service-private-l1-1-0!I_ScRegisterDeviceNotification` at `0x18005555a`
- `api-ms-win-service-private-l1-1-0!I_ScRegisterDeviceNotification` at `0x18005555a`

## pseudocode

```c
__int64 __fastcall PfDiVolumeAdd(__int64 *a1, unsigned __int8 *a2, int a3)
{
  __int128 *v3; // r13
  HANDLE FileW; // rax
  __int64 v7; // r12
  void *v8; // rdi
  DWORD LastError; // ebx
  __int64 v10; // rax
  __int64 v11; // rcx
  __int16 v12; // ax
  __int64 v13; // rcx
  __int64 v14; // r8
  __int128 v15; // xmm1
  __int64 v16; // rax
  __int64 v17; // rcx
  __int128 v18; // xmm0
  __int64 v20; // [rsp+48h] [rbp-61h] BYREF
  __int128 v21; // [rsp+50h] [rbp-59h] BYREF
  __int128 v22; // [rsp+60h] [rbp-49h]
  __int128 v23; // [rsp+70h] [rbp-39h]
  unsigned __int8 *v24; // [rsp+80h] [rbp-29h]
  __int128 v25; // [rsp+88h] [rbp-21h] BYREF
  __int128 v26; // [rsp+98h] [rbp-11h]
  __int128 v27; // [rsp+A8h] [rbp-1h]
  __int64 v28; // [rsp+B8h] [rbp+Fh]

  v24 = a2;
  v3 = &v21;
  v28 = 0;
  v20 = 0;
  v25 = 0;
  v26 = 0;
  v27 = 0;
  v21 = 0;
  v22 = 0;
  v23 = 0;
  FileW = CreateFileW((LPCWSTR)a2, 0, 7u, 0, 3u, 0, 0);
  v7 = -1;
  v8 = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
LABEL_22:
    PfDiVolumeCleanup(v3);
    return LastError;
  }
  LastError = PfDiVolumeIsSupported(FileW);
  if ( !LastError )
  {
    do
      ++v7;
    while ( *(_WORD *)&v24[2 * v7] );
    v10 = PfScStringInsertEx(*(_QWORD *)&PfSvcGlobals + 96LL, v24, v7, 0);
    v11 = v10;
    if ( !v10 )
      goto LABEL_6;
    v12 = *(_WORD *)(v10 + 28);
    *(_QWORD *)&v22 = v11;
    WORD4(v22) = v12;
    WORD5(v22) = 1;
    DWORD2(v23) = 2;
    PfDiVolumeProcessDismount(&v21, 0);
    v13 = *(_QWORD *)(*(_QWORD *)&PfSvcGlobals + 1464LL);
    if ( v13 )
    {
      v25 = 0x600000038uLL;
      v26 = (unsigned __int64)v8;
      v27 = 0;
      v28 = 0;
      *(_QWORD *)&v23 = I_ScRegisterDeviceNotification(v13, &v25, 1);
      if ( !(_QWORD)v23 )
        goto LABEL_21;
      LastError = PfDiVolumeGetDeviceInfo(v8, &v20);
      if ( LastError )
        goto LABEL_21;
      if ( (BYTE8(v23) & 1) != 0 )
      {
        if ( (v20 & 0x2000000000LL) != 0 )
        {
          LastError = PfDiVolumeProcessMount(&v21, v8, v14, a3 | 3u);
          if ( LastError )
            goto LABEL_21;
        }
        else if ( (a3 & 4) != 0 && !(unsigned int)PfDiGetVolumeInfo(v8, &v21) )
        {
          DWORD2(v23) &= ~2u;
        }
      }
      else if ( (v20 & 0x2000000000LL) == 0 )
      {
        PfDiVolumeProcessDismount(&v21, 0);
      }
    }
    if ( !(unsigned __int8)PfArrayGrow(*((unsigned int *)a1 + 2), 48, (char *)a1 + 12, a1) )
    {
LABEL_6:
      LastError = 8;
      goto LABEL_21;
    }
    v3 = 0;
    LastError = 0;
    v15 = v22;
    v16 = *a1;
    v17 = 6LL * *((unsigned int *)a1 + 2);
    *(_OWORD *)(v16 + 8 * v17) = v21;
    v18 = v23;
    *(_OWORD *)(v16 + 8 * v17 + 16) = v15;
    *(_OWORD *)(v16 + 8 * v17 + 32) = v18;
    ++*((_DWORD *)a1 + 2);
  }
LABEL_21:
  CloseHandle(v8);
  if ( v3 )
    goto LABEL_22;
  return LastError;
}

```

## disassembly

```asm
0x1800553b8  mov     [rsp-8+arg_10], rbx
0x1800553bd  push    rbp
0x1800553be  push    rsi
0x1800553bf  push    rdi
0x1800553c0  push    r12
0x1800553c2  push    r13
0x1800553c4  push    r14
0x1800553c6  push    r15
0x1800553c8  lea     rbp, [rsp-27h]
0x1800553cd  sub     rsp, 0D0h
0x1800553d4  mov     rax, cs:__security_cookie
0x1800553db  xor     rax, rsp
0x1800553de  mov     [rbp+57h+var_40], rax
0x1800553e2  xorps   xmm0, xmm0
0x1800553e5  mov     [rbp+57h+var_80], rdx
0x1800553e9  xor     r15d, r15d
0x1800553ec  lea     r13, [rbp+57h+var_B0]
0x1800553f0  mov     rsi, rcx
0x1800553f3  mov     [rsp+100h+hTemplateFile], r15; hTemplateFile
0x1800553f8  xor     ecx, ecx
0x1800553fa  mov     [rsp+100h+dwFlagsAndAttributes], r15d; dwFlagsAndAttributes
0x1800553ff  mov     rax, rdx
0x180055402  mov     [rbp+57h+var_48], rcx
0x180055406  mov     r14d, r8d
0x180055409  mov     [rbp+57h+var_B8], r15
0x18005540d  xor     r9d, r9d; lpSecurityAttributes
0x180055410  mov     [rbp+57h+var_C0], r15d
0x180055414  lea     r8d, [rcx+7]; dwShareMode
0x180055418  mov     [rsp+100h+dwCreationDisposition], 3; dwCreationDisposition
0x180055420  mov     rcx, rax; lpFileName
0x180055423  xor     edx, edx; dwDesiredAccess
0x180055425  movups  [rbp+57h+var_78], xmm0
0x180055429  movups  [rbp+57h+var_68], xmm0
0x18005542d  movups  [rbp+57h+var_58], xmm0
0x180055431  movups  [rbp+57h+var_B0], xmm0
0x180055435  movups  [rbp+57h+var_A0], xmm0
0x180055439  movups  [rbp+57h+var_90], xmm0
0x18005543d  call    cs:__imp_CreateFileW
0x180055443  or      r12, 0FFFFFFFFFFFFFFFFh
0x180055447  mov     rdi, rax
0x18005544a  cmp     rax, r12
0x18005544d  jnz     short loc_18005545C
0x18005544f  call    cs:__imp_GetLastError
0x180055455  mov     ebx, eax
0x180055457  jmp     loc_180055632
0x18005545c  lea     r8, [rbp+57h+var_C0]
0x180055460  mov     rcx, rdi; hDevice
0x180055463  lea     rdx, [rbp+57h+var_B8]
0x180055467  call    PfDiVolumeIsSupported
0x18005546c  mov     ebx, eax
0x18005546e  test    eax, eax
0x180055470  jnz     loc_180055624
0x180055476  lea     ecx, [rax+4]
0x180055479  xor     eax, eax
0x18005547b  cmp     [rbp+57h+var_C0], eax
0x18005547e  jz      short loc_180055486
0x180055480  mov     dword ptr [rbp+57h+var_90+8], ecx
0x180055483  mov     r15d, ecx
0x180055486  test    byte ptr [rbp+57h+var_B8+4], 20h
0x18005548a  jz      short loc_1800554B2
0x18005548c  mov     r9d, r14d
0x18005548f  lea     rcx, [rbp+57h+var_B0]
0x180055493  or      r9d, 3
0x180055497  mov     rdx, rdi
0x18005549a  call    PfDiVolumeProcessMount
0x18005549f  xor     r15d, r15d
0x1800554a2  mov     ebx, eax
0x1800554a4  test    eax, eax
0x1800554a6  jnz     loc_180055624
0x1800554ac  lea     r12d, [rax+1]
0x1800554b0  jmp     short loc_180055515
0x1800554b2  mov     rdx, [rbp+57h+var_80]
0x1800554b6  inc     r12
0x1800554b9  cmp     [rdx+r12*2], ax
0x1800554be  jnz     short loc_1800554B6
0x1800554c0  mov     rcx, cs:PfSvcGlobals
0x1800554c7  xor     r9d, r9d
0x1800554ca  add     rcx, 60h ; '`'
0x1800554ce  mov     r8d, r12d
0x1800554d1  call    PfScStringInsertEx
0x1800554d6  mov     rcx, rax
0x1800554d9  test    rax, rax
0x1800554dc  jnz     short loc_1800554E8
0x1800554de  mov     ebx, 8
0x1800554e3  jmp     loc_180055624
0x1800554e8  movzx   eax, word ptr [rax+1Ch]
0x1800554ec  mov     r12d, 1
0x1800554f2  mov     qword ptr [rbp+57h+var_A0], rcx
0x1800554f6  or      r15d, 2
0x1800554fa  lea     rcx, [rbp+57h+var_B0]
0x1800554fe  mov     word ptr [rbp+57h+var_A0+8], ax
0x180055502  xor     edx, edx
0x180055504  mov     word ptr [rbp+57h+var_A0+0Ah], r12w
0x180055509  mov     dword ptr [rbp+57h+var_90+8], r15d
0x18005550d  call    PfDiVolumeProcessDismount
0x180055512  xor     r15d, r15d
0x180055515  mov     rax, cs:PfSvcGlobals
0x18005551c  mov     rcx, [rax+5B8h]
0x180055523  test    rcx, rcx
0x180055526  jz      loc_1800555D7
0x18005552c  xorps   xmm0, xmm0
0x18005552f  lea     rdx, [rbp+57h+var_78]
0x180055533  movups  [rbp+57h+var_78], xmm0
0x180055537  xor     eax, eax
0x180055539  mov     dword ptr [rbp+57h+var_78], 38h ; '8'
0x180055540  movups  [rbp+57h+var_68], xmm0
0x180055544  mov     r8d, r12d
0x180055547  mov     dword ptr [rbp+57h+var_78+4], 6
0x18005554e  mov     qword ptr [rbp+57h+var_68], rdi
0x180055552  movups  [rbp+57h+var_58], xmm0
0x180055556  mov     [rbp+57h+var_48], rax
0x18005555a  call    cs:__imp_I_ScRegisterDeviceNotification
0x180055560  mov     qword ptr [rbp+57h+var_90], rax
0x180055564  test    rax, rax
0x180055567  jz      loc_180055624
0x18005556d  lea     rdx, [rbp+57h+var_B8]
0x180055571  mov     rcx, rdi
0x180055574  call    PfDiVolumeGetDeviceInfo
0x180055579  mov     ebx, eax
0x18005557b  test    eax, eax
0x18005557d  jnz     loc_180055624
0x180055583  test    byte ptr [rbp+57h+var_90+8], r12b
0x180055587  jz      short loc_1800555C6
0x180055589  test    byte ptr [rbp+57h+var_B8+4], 20h
0x18005558d  jz      short loc_1800555AA
0x18005558f  or      r14d, 3
0x180055593  lea     rcx, [rbp+57h+var_B0]
0x180055597  mov     r9d, r14d
0x18005559a  mov     rdx, rdi
0x18005559d  call    PfDiVolumeProcessMount
0x1800555a2  mov     ebx, eax
0x1800555a4  test    eax, eax
0x1800555a6  jz      short loc_1800555D7
0x1800555a8  jmp     short loc_180055624
0x1800555aa  test    r14b, 4
0x1800555ae  jz      short loc_1800555D7
0x1800555b0  lea     rdx, [rbp+57h+var_B0]
0x1800555b4  mov     rcx, rdi
0x1800555b7  call    PfDiGetVolumeInfo
0x1800555bc  test    eax, eax
0x1800555be  jnz     short loc_1800555D7
0x1800555c0  and     dword ptr [rbp+57h+var_90+8], 0FFFFFFFDh
0x1800555c4  jmp     short loc_1800555D7
0x1800555c6  test    byte ptr [rbp+57h+var_B8+4], 20h
0x1800555ca  jnz     short loc_1800555D7
0x1800555cc  xor     edx, edx
0x1800555ce  lea     rcx, [rbp+57h+var_B0]
0x1800555d2  call    PfDiVolumeProcessDismount
0x1800555d7  mov     ecx, [rsi+8]
0x1800555da  lea     r8, [rsi+0Ch]
0x1800555de  mov     r9, rsi
0x1800555e1  mov     edx, 30h ; '0'
0x1800555e6  call    PfArrayGrow
0x1800555eb  test    al, al
0x1800555ed  jz      loc_1800554DE
0x1800555f3  mov     eax, [rsi+8]
0x1800555f6  mov     r13, r15
0x1800555f9  movups  xmm0, [rbp+57h+var_B0]
0x1800555fd  mov     ebx, r15d
0x180055600  movups  xmm1, [rbp+57h+var_A0]
0x180055604  lea     rcx, [rax+rax*2]
0x180055608  mov     rax, [rsi]
0x18005560b  add     rcx, rcx
0x18005560e  movups  xmmword ptr [rax+rcx*8], xmm0
0x180055612  movups  xmm0, [rbp+57h+var_90]
0x180055616  movups  xmmword ptr [rax+rcx*8+10h], xmm1
0x18005561b  movups  xmmword ptr [rax+rcx*8+20h], xmm0
0x180055620  add     [rsi+8], r12d
0x180055624  mov     rcx, rdi; hObject
0x180055627  call    cs:__imp_CloseHandle
0x18005562d  test    r13, r13
0x180055630  jz      short loc_18005563A
0x180055632  mov     rcx, r13
0x180055635  call    PfDiVolumeCleanup
0x18005563a  mov     eax, ebx
0x18005563c  mov     rcx, [rbp+57h+var_40]
0x180055640  xor     rcx, rsp; StackCookie
0x180055643  call    __security_check_cookie
0x180055648  mov     rbx, [rsp+100h+arg_10]
0x180055650  add     rsp, 0D0h
0x180055657  pop     r15
0x180055659  pop     r14
0x18005565b  pop     r13
0x18005565d  pop     r12
0x18005565f  pop     rdi
0x180055660  pop     rsi
0x180055661  pop     rbp
0x180055662  retn
```
