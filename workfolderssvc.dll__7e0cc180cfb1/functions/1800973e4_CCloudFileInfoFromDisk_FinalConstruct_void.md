# CCloudFileInfoFromDisk::FinalConstruct(void *)

- ea: `0x1800973e4`
- end: `0x180097771`
- name: `?FinalConstruct@CCloudFileInfoFromDisk@@IEAAJPEAX@Z`
- size: `909`
- prototype: `__int64 __fastcall(CCloudFileInfoFromDisk *__hidden this, void *)`
- caller_count: `2`
- callee_count: `7`
- tags: `reparse_path, loader_planting`

## callers

- `0x180096eb4`
- `0x180097778`

## callees

- `0x180002ab0`
- `0x180006f5c`
- `0x18001137c`
- `0x1800973e4`
- `0x180097acc`
- `0x180097c5c`
- `0x180097cf0`

## import_xrefs

- `KERNEL32!GetFinalPathNameByHandleW` at `0x18009766e`
- `KERNEL32!GetFinalPathNameByHandleW` at `0x1800976e6`
- `KERNEL32!GetFinalPathNameByHandleW` at `0x18009766e`
- `KERNEL32!GetFinalPathNameByHandleW` at `0x1800976e6`
- `KERNEL32!GetLastError` at `0x18009767b`
- `KERNEL32!GetLastError` at `0x180097685`
- `KERNEL32!GetLastError` at `0x180097692`
- `KERNEL32!GetLastError` at `0x18009767b`
- `KERNEL32!GetLastError` at `0x180097685`
- `KERNEL32!GetLastError` at `0x180097692`
- `ntdll!NtQueryInformationFile` at `0x180097496`
- `ntdll!NtQueryInformationFile` at `0x1800974cb`
- `ntdll!NtQueryInformationFile` at `0x180097501`
- `ntdll!NtQueryInformationFile` at `0x180097496`
- `ntdll!NtQueryInformationFile` at `0x1800974cb`
- `ntdll!NtQueryInformationFile` at `0x180097501`
- `ntdll!NtFsControlFile` at `0x180097560`
- `ntdll!NtFsControlFile` at `0x180097560`

## pseudocode

```c
__int64 __fastcall CCloudFileInfoFromDisk::FinalConstruct(CCloudFileInfoFromDisk *this, void *a2)
{
  NTSTATUS v4; // ebx
  const unsigned __int16 *v5; // r15
  int v6; // ecx
  bool v7; // zf
  __int128 v8; // xmm0
  __int64 v9; // rax
  int v10; // eax
  __int64 v11; // rax
  __int128 v12; // xmm0
  unsigned __int64 v13; // r14
  unsigned __int16 *v14; // rcx
  WCHAR *v15; // rdx
  DWORD v16; // r12d
  WCHAR *v17; // r15
  DWORD FinalPathNameByHandleW; // eax
  DWORD v19; // r14d
  int v20; // eax
  __int64 v21; // rcx
  DWORD v22; // eax
  char *v23; // r9
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+50h] [rbp-B0h] BYREF
  int InputBuffer; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v27; // [rsp+68h] [rbp-98h] BYREF
  int v28; // [rsp+70h] [rbp-90h] BYREF
  __int128 v29; // [rsp+74h] [rbp-8Ch]
  __int128 v30; // [rsp+84h] [rbp-7Ch]
  int v31; // [rsp+94h] [rbp-6Ch]
  int FileInformation; // [rsp+98h] [rbp-68h] BYREF
  __int128 v33; // [rsp+9Ch] [rbp-64h]
  int v34; // [rsp+ACh] [rbp-54h]
  _BYTE OutputBuffer[8]; // [rsp+B0h] [rbp-50h] BYREF
  __int128 v36; // [rsp+B8h] [rbp-48h]
  __int128 v37; // [rsp+C8h] [rbp-38h]
  __int64 v38; // [rsp+D8h] [rbp-28h]
  unsigned __int16 v39; // [rsp+F8h] [rbp-8h]
  unsigned __int16 v40; // [rsp+FAh] [rbp-6h]

  *((_DWORD *)this + 98) = 0;
  *((_QWORD *)this + 50) = 0;
  *((_QWORD *)this + 51) = 0;
  HIDWORD(IoStatusBlock.Pointer) = 0;
  FileInformation = 0;
  v34 = 0;
  v27 = 0;
  v28 = 0;
  v31 = 0;
  v33 = 0;
  v29 = 0;
  v30 = 0;
  if ( !a2 )
    return (unsigned int)-1073741811;
  IoStatusBlock.Information = 0;
  IoStatusBlock.Status = -1073741823;
  v4 = NtQueryInformationFile(a2, &IoStatusBlock, &FileInformation, 0x18u, FileStandardInformation);
  if ( v4 >= 0 )
  {
    IoStatusBlock.Status = -1073741823;
    IoStatusBlock.Information = 0;
    v4 = NtQueryInformationFile(a2, &IoStatusBlock, &v27, 8u, FileAttributeTagInformation);
    if ( v4 >= 0 )
    {
      IoStatusBlock.Status = -1073741823;
      IoStatusBlock.Information = 0;
      v4 = NtQueryInformationFile(a2, &IoStatusBlock, &v28, 0x28u, FileBasicInformation);
      if ( v4 >= 0 )
      {
        InputBuffer = 196611;
        IoStatusBlock.Status = -1073741823;
        IoStatusBlock.Information = 0;
        v4 = NtFsControlFile(a2, 0, 0, 0, &IoStatusBlock, 0x900EBu, &InputBuffer, 4u, OutputBuffer, 0x250u);
        if ( v4 >= 0 )
        {
          v5 = (const unsigned __int16 *)&OutputBuffer[v40];
          v5[(unsigned __int64)v39 >> 1] = 0;
          v6 = HIDWORD(v30);
          v7 = (BYTE12(v30) & 0x10) == 0;
          v8 = v36;
          *((_DWORD *)this + 7) = v28;
          *((_DWORD *)this + 8) = v29;
          *((_DWORD *)this + 9) = HIDWORD(v29);
          *((_QWORD *)this + 5) = v30;
          *((_DWORD *)this + 12) = DWORD2(v30);
          v9 = 0;
          if ( v7 )
            v9 = *(_QWORD *)((char *)&v33 + 4);
          *((_QWORD *)this + 7) = v9;
          *((_QWORD *)this + 8) = v38;
          *((_DWORD *)this + 18) = HIDWORD(v27);
          v10 = HIDWORD(v33);
          *(_OWORD *)((char *)this + 8) = v8;
          *((_DWORD *)this + 19) = v10;
          v11 = -1;
          v12 = v37;
          *((_DWORD *)this + 6) = v6;
          *((_OWORD *)this + 5) = v12;
          do
            ++v11;
          while ( v5[v11] );
          v13 = v11 + 1;
          if ( (int)CEcsPreallocArray<unsigned short,30>::ReAlloc((unsigned __int64 *)this + 12, v11 + 1) < 0 )
            return (unsigned int)-1073741664;
          v14 = (unsigned __int16 *)*((_QWORD *)this + 13);
          if ( !v14 )
            v14 = (unsigned __int16 *)((char *)this + 112);
          if ( StringCchCopyW(v14, v13, v5) < 0 )
            return (unsigned int)-2147483643;
          v15 = (WCHAR *)*((_QWORD *)this + 23);
          v16 = *((_DWORD *)this + 44);
          if ( !v15 )
            v15 = (WCHAR *)((char *)this + 192);
          v17 = (WCHAR *)((char *)this + 192);
          FinalPathNameByHandleW = GetFinalPathNameByHandleW(a2, v15, v16, 0);
          v19 = FinalPathNameByHandleW;
          if ( !FinalPathNameByHandleW )
            goto LABEL_20;
          if ( FinalPathNameByHandleW <= v16 )
            goto LABEL_34;
          v20 = CEcsPreallocArray<unsigned short,100>::ReAlloc((unsigned __int64 *)this + 22, FinalPathNameByHandleW);
          v21 = *((_QWORD *)this + 23);
          if ( !v21 && this == (CCloudFileInfoFromDisk *)-192LL || v20 < 0 )
            return (unsigned int)-1073741664;
          if ( v21 )
            v17 = (WCHAR *)*((_QWORD *)this + 23);
          v22 = GetFinalPathNameByHandleW(a2, v17, v19, 0);
          if ( v22 && v22 <= v19 )
          {
LABEL_34:
            if ( CCloudFileInfoFromDisk::QueryCloudFilesState(this, a2) < 0
              && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x20) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 3u )
            {
              v23 = (char *)*((_QWORD *)this + 13);
              if ( !v23 )
                v23 = (char *)this + 112;
              WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 7), 10, WPP_f8e6fa06510b319a2a826975932f738e_Traceguids, v23);
            }
          }
          else
          {
LABEL_20:
            if ( (int)GetLastError() > 0 )
              return (unsigned __int16)GetLastError() | 0xC0070000;
            else
              return GetLastError();
          }
        }
      }
    }
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800973e4  mov     [rsp-8+arg_10], rbx
0x1800973e9  push    rbp
0x1800973ea  push    rsi
0x1800973eb  push    rdi
0x1800973ec  push    r12
0x1800973ee  push    r13
0x1800973f0  push    r14
0x1800973f2  push    r15
0x1800973f4  lea     rbp, [rsp-220h]
0x1800973fc  sub     rsp, 320h
0x180097403  mov     rax, cs:__security_cookie
0x18009740a  xor     rax, rsp
0x18009740d  mov     [rbp+250h+var_40], rax
0x180097414  xor     r12d, r12d
0x180097417  xor     eax, eax
0x180097419  mov     [rcx+188h], r12d
0x180097420  xorps   xmm0, xmm0
0x180097423  mov     [rcx+190h], r12
0x18009742a  mov     rsi, rdx
0x18009742d  mov     [rcx+198h], r12
0x180097434  mov     rdi, rcx
0x180097437  mov     dword ptr [rsp+350h+IoStatusBlock+4], r12d
0x18009743c  mov     [rbp+250h+FileInformation], r12d
0x180097440  mov     [rbp+250h+var_2A4], eax
0x180097443  mov     [rsp+350h+var_2E8], r12
0x180097448  mov     [rsp+350h+var_2E0], r12d
0x18009744d  mov     [rbp+250h+var_2BC], eax
0x180097450  movups  [rbp+250h+var_2B4], xmm0
0x180097454  movups  [rsp+350h+var_2DC], xmm0
0x180097459  movups  [rbp+250h+var_2CC], xmm0
0x18009745d  test    rdx, rdx
0x180097460  jnz     short loc_18009746C
0x180097462  mov     ebx, 0C000000Dh
0x180097467  jmp     loc_180097745
0x18009746c  mov     r14d, 0C0000001h
0x180097472  mov     [rsp+350h+IoStatusBlock.Information], r12
0x180097477  mov     r9d, 18h; Length
0x18009747d  mov     dword ptr [rsp+350h+IoStatusBlock], r14d
0x180097482  lea     r8, [rbp+250h+FileInformation]; FileInformation
0x180097486  mov     [rsp+350h+FileInformationClass], 5; FileInformationClass
0x18009748e  lea     rdx, [rsp+350h+IoStatusBlock]; IoStatusBlock
0x180097493  mov     rcx, rsi; FileHandle
0x180097496  call    cs:__imp_NtQueryInformationFile
0x18009749c  mov     ebx, eax
0x18009749e  test    eax, eax
0x1800974a0  js      loc_180097745
0x1800974a6  mov     r9d, 8; Length
0x1800974ac  mov     dword ptr [rsp+350h+IoStatusBlock], r14d
0x1800974b1  lea     r8, [rsp+350h+var_2E8]; FileInformation
0x1800974b6  mov     [rsp+350h+IoStatusBlock.Information], r12
0x1800974bb  lea     rdx, [rsp+350h+IoStatusBlock]; IoStatusBlock
0x1800974c0  mov     [rsp+350h+FileInformationClass], 23h ; '#'; FileInformationClass
0x1800974c8  mov     rcx, rsi; FileHandle
0x1800974cb  call    cs:__imp_NtQueryInformationFile
0x1800974d1  mov     ebx, eax
0x1800974d3  test    eax, eax
0x1800974d5  js      loc_180097745
0x1800974db  mov     r15d, 4
0x1800974e1  mov     dword ptr [rsp+350h+IoStatusBlock], r14d
0x1800974e6  lea     r8, [rsp+350h+var_2E0]; FileInformation
0x1800974eb  mov     [rsp+350h+IoStatusBlock.Information], r12
0x1800974f0  lea     rdx, [rsp+350h+IoStatusBlock]; IoStatusBlock
0x1800974f5  mov     [rsp+350h+FileInformationClass], r15d; FileInformationClass
0x1800974fa  mov     rcx, rsi; FileHandle
0x1800974fd  lea     r9d, [r15+24h]; Length
0x180097501  call    cs:__imp_NtQueryInformationFile
0x180097507  mov     ebx, eax
0x180097509  test    eax, eax
0x18009750b  js      loc_180097745
0x180097511  mov     [rsp+350h+OutputBufferLength], 250h; OutputBufferLength
0x180097519  lea     rax, [rbp+250h+var_2A0]
0x18009751d  mov     [rsp+350h+OutputBuffer], rax; OutputBuffer
0x180097522  xor     r9d, r9d; ApcContext
0x180097525  mov     [rsp+350h+InputBufferLength], r15d; InputBufferLength
0x18009752a  lea     rax, [rsp+350h+var_2F0]
0x18009752f  mov     [rsp+350h+InputBuffer], rax; InputBuffer
0x180097534  xor     r8d, r8d; ApcRoutine
0x180097537  lea     rax, [rsp+350h+IoStatusBlock]
0x18009753c  mov     [rsp+350h+FsControlCode], 900EBh; FsControlCode
0x180097544  xor     edx, edx; Event
0x180097546  mov     qword ptr [rsp+350h+FileInformationClass], rax; IoStatusBlock
0x18009754b  mov     rcx, rsi; FileHandle
0x18009754e  mov     [rsp+350h+var_2F0], 30003h
0x180097556  mov     dword ptr [rsp+350h+IoStatusBlock], r14d
0x18009755b  mov     [rsp+350h+IoStatusBlock.Information], r12
0x180097560  call    cs:__imp_NtFsControlFile
0x180097566  mov     ebx, eax
0x180097568  test    eax, eax
0x18009756a  js      loc_180097745
0x180097570  movzx   eax, [rbp+250h+var_256]
0x180097574  lea     r15, [rbp+250h+var_2A0]
0x180097578  movzx   ecx, [rbp+250h+var_258]
0x18009757c  add     r15, rax
0x18009757f  shr     rcx, 1
0x180097582  mov     [r15+rcx*2], r12w
0x180097587  mov     eax, [rsp+350h+var_2E0]
0x18009758b  mov     ecx, dword ptr [rbp+250h+var_2CC+0Ch]
0x18009758e  test    cl, 10h
0x180097591  movups  xmm0, [rbp+250h+var_298]
0x180097595  mov     [rdi+1Ch], eax
0x180097598  mov     eax, dword ptr [rsp+350h+var_2DC]
0x18009759c  mov     [rdi+20h], eax
0x18009759f  mov     eax, dword ptr [rbp+250h+var_2DC+0Ch]
0x1800975a2  mov     [rdi+24h], eax
0x1800975a5  mov     eax, dword ptr [rbp+250h+var_2CC]
0x1800975a8  mov     [rdi+28h], eax
0x1800975ab  mov     eax, dword ptr [rbp+250h+var_2CC+4]
0x1800975ae  mov     [rdi+2Ch], eax
0x1800975b1  mov     eax, dword ptr [rbp+250h+var_2CC+8]
0x1800975b4  mov     [rdi+30h], eax
0x1800975b7  mov     rax, r12
0x1800975ba  cmovz   rax, qword ptr [rbp+250h+var_2B4+4]
0x1800975bf  mov     [rdi+38h], rax
0x1800975c3  mov     rax, [rbp+250h+var_278]
0x1800975c7  mov     [rdi+40h], rax
0x1800975cb  mov     eax, dword ptr [rsp+350h+var_2E8+4]
0x1800975cf  mov     [rdi+48h], eax
0x1800975d2  mov     eax, dword ptr [rbp+250h+var_2B4+0Ch]
0x1800975d5  movdqu  xmmword ptr [rdi+8], xmm0
0x1800975da  mov     [rdi+4Ch], eax
0x1800975dd  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800975e1  movups  xmm0, [rbp+250h+var_288]
0x1800975e5  mov     [rdi+18h], ecx
0x1800975e8  movdqu  xmmword ptr [rdi+50h], xmm0
0x1800975ed  inc     rax
0x1800975f0  cmp     [r15+rax*2], r12w
0x1800975f5  jnz     short loc_1800975ED
0x1800975f7  lea     r14, [rax+1]
0x1800975fb  mov     rdx, r14
0x1800975fe  lea     rcx, [rdi+60h]
0x180097602  call    ?ReAlloc@?$CEcsPreallocArray@G$0BO@@@QEAAJ_K@Z; CEcsPreallocArray<ushort,30>::ReAlloc(unsigned __int64)
0x180097607  test    eax, eax
0x180097609  jns     short loc_180097615
0x18009760b  mov     ebx, 0C00000A0h
0x180097610  jmp     loc_180097745
0x180097615  mov     rcx, [rdi+68h]
0x180097619  test    rcx, rcx
0x18009761c  jnz     short loc_180097622
0x18009761e  lea     rcx, [rdi+70h]; unsigned __int16 *
0x180097622  mov     r8, r15; unsigned __int16 *
0x180097625  mov     rdx, r14; unsigned __int64
0x180097628  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18009762d  test    eax, eax
0x18009762f  jns     short loc_18009763B
0x180097631  mov     ebx, 80000005h
0x180097636  jmp     loc_180097745
0x18009763b  mov     rdx, [rdi+0B8h]
0x180097642  lea     r13, [rdi+0B0h]
0x180097649  mov     r12d, [r13+0]
0x18009764d  test    rdx, rdx
0x180097650  jz      short loc_18009765B
0x180097652  lea     r15, [rdi+0C0h]
0x180097659  jmp     short loc_180097665
0x18009765b  lea     rdx, [rdi+0C0h]; lpszFilePath
0x180097662  mov     r15, rdx
0x180097665  xor     r9d, r9d; dwFlags
0x180097668  mov     r8d, r12d; cchFilePath
0x18009766b  mov     rcx, rsi; hFile
0x18009766e  call    cs:__imp_GetFinalPathNameByHandleW
0x180097674  mov     r14d, eax
0x180097677  test    eax, eax
0x180097679  jnz     short loc_1800976A6
0x18009767b  call    cs:__imp_GetLastError
0x180097681  test    eax, eax
0x180097683  jg      short loc_180097692
0x180097685  call    cs:__imp_GetLastError
0x18009768b  mov     ebx, eax
0x18009768d  jmp     loc_180097745
0x180097692  call    cs:__imp_GetLastError
0x180097698  movzx   ebx, ax
0x18009769b  or      ebx, 0C0070000h
0x1800976a1  jmp     loc_180097745
0x1800976a6  cmp     r14d, r12d
0x1800976a9  jbe     short loc_1800976F5
0x1800976ab  mov     rdx, r14
0x1800976ae  mov     rcx, r13
0x1800976b1  call    ?ReAlloc@?$CEcsPreallocArray@G$0GE@@@QEAAJ_K@Z; CEcsPreallocArray<ushort,100>::ReAlloc(unsigned __int64)
0x1800976b6  mov     rcx, [rdi+0B8h]
0x1800976bd  test    rcx, rcx
0x1800976c0  jnz     short loc_1800976CB
0x1800976c2  test    r15, r15
0x1800976c5  jz      loc_18009760B
0x1800976cb  test    eax, eax
0x1800976cd  js      loc_18009760B
0x1800976d3  test    rcx, rcx
0x1800976d6  mov     r8d, r14d; cchFilePath
0x1800976d9  cmovnz  r15, rcx
0x1800976dd  xor     r9d, r9d; dwFlags
0x1800976e0  mov     rdx, r15; lpszFilePath
0x1800976e3  mov     rcx, rsi; hFile
0x1800976e6  call    cs:__imp_GetFinalPathNameByHandleW
0x1800976ec  test    eax, eax
0x1800976ee  jz      short loc_18009767B
0x1800976f0  cmp     eax, r14d
0x1800976f3  ja      short loc_18009767B
0x1800976f5  mov     rdx, rsi; void *
0x1800976f8  mov     rcx, rdi; this
0x1800976fb  call    ?QueryCloudFilesState@CCloudFileInfoFromDisk@@AEAAJPEAX@Z; CCloudFileInfoFromDisk::QueryCloudFilesState(void *)
0x180097700  test    eax, eax
0x180097702  jns     short loc_180097745
0x180097704  mov     rcx, cs:WPP_GLOBAL_Control
0x18009770b  lea     rax, WPP_GLOBAL_Control
0x180097712  cmp     rcx, rax
0x180097715  jz      short loc_180097745
0x180097717  test    byte ptr [rcx+44h], 20h
0x18009771b  jz      short loc_180097745
0x18009771d  cmp     byte ptr [rcx+41h], 3
0x180097721  jb      short loc_180097745
0x180097723  mov     r9, [rdi+68h]
0x180097727  test    r9, r9
0x18009772a  jnz     short loc_180097730
0x18009772c  lea     r9, [rdi+70h]
0x180097730  mov     rcx, [rcx+38h]
0x180097734  lea     r8, WPP_f8e6fa06510b319a2a826975932f738e_Traceguids
0x18009773b  mov     edx, 0Ah
0x180097740  call    WPP_SF_S
0x180097745  mov     eax, ebx
0x180097747  mov     rcx, [rbp+250h+var_40]
0x18009774e  xor     rcx, rsp; StackCookie
0x180097751  call    __security_check_cookie
0x180097756  mov     rbx, [rsp+350h+arg_10]
0x18009775e  add     rsp, 320h
0x180097765  pop     r15
0x180097767  pop     r14
0x180097769  pop     r13
0x18009776b  pop     r12
0x18009776d  pop     rdi
0x18009776e  pop     rsi
0x18009776f  pop     rbp
0x180097770  retn
```
