# CEseLayerPhysicalDatabase::AttachPhysicalDatabaseInternal(ushort const *,ushort const *,ushort const *,ulong,bool,ulong,ushort const * const,CEseLayerPhysicalDatabase * *)

- ea: `0x1800433f4`
- end: `0x1800436ba`
- name: `?AttachPhysicalDatabaseInternal@CEseLayerPhysicalDatabase@@CAJPEBG00K_NKQEBGPEAPEAV1@@Z`
- size: `710`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, unsigned int, bool, unsigned int, const unsigned __int16 *const, struct CEseLayerPhysicalDatabase **)`
- caller_count: `3`
- callee_count: `14`
- tags: `file_ops, authz_impersonation`

## callers

- `0x180008000`
- `0x180009390`
- `0x1800433f4`

## callees

- `0x18000d838`
- `0x180042a18`
- `0x180042c14`
- `0x1800433f4`
- `0x1800436c0`
- `0x180080fb0`
- `0x1800814bc`
- `0x1800a7180`
- `0x1800b0a30`
- `0x1800b7fa0`
- `0x1800b9288`
- `0x1800c5094`
- `0x1800c52ac`
- `0x1800c5324`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18004362d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18004362d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180043640`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180043662`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180043640`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180043662`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043511`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043685`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043511`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043685`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180043542`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180043542`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180043505`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180043505`

## pseudocode

```c
__int64 __fastcall CEseLayerPhysicalDatabase::AttachPhysicalDatabaseInternal(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        unsigned __int16 *a3,
        unsigned int a4,
        bool a5,
        unsigned int a6,
        unsigned __int16 *a7,
        struct CEseLayerPhysicalDatabase **a8)
{
  unsigned __int16 *v9; // rbp
  unsigned __int16 *v11; // r14
  signed int EseInstanceInternal; // ebx
  struct CEseInstance *v14; // rax
  unsigned __int64 *v15; // r14
  CEseLayerPhysicalDatabase *v16; // rdi
  unsigned __int64 v17; // r9
  int v18; // eax
  unsigned int v19; // edx
  unsigned int v20; // edx
  int v21; // edx
  int v22; // ecx
  int v23; // r8d
  BOOL v24; // ebp
  unsigned int i; // edi
  signed int LastError; // eax
  unsigned int v27; // edi
  char CurrentProcessId; // al
  int v30; // edx
  int v31; // ecx
  int v32; // r8d
  DWORD v33; // eax
  int v34; // edx
  int v35; // ecx
  DWORD v36; // eax
  bool v37; // [rsp+40h] [rbp-298h] BYREF
  unsigned __int16 *v38; // [rsp+48h] [rbp-290h]
  unsigned __int16 *v39; // [rsp+50h] [rbp-288h]
  struct CEseInstance *v40[3]; // [rsp+58h] [rbp-280h] BYREF
  WCHAR Filename[264]; // [rsp+70h] [rbp-268h] BYREF

  v9 = a7;
  v11 = a3;
  v38 = a3;
  *a8 = 0;
  v39 = a7;
  v40[0] = 0;
  EseInstanceInternal = CEseInstance::CreateEseInstanceInternal(v40, a1, a4, 1, a3);
  if ( EseInstanceInternal >= 0 )
  {
    EseInstanceInternal = -2147024882;
    v14 = (struct CEseInstance *)operator new(0x288u);
    v15 = (unsigned __int64 *)v40[0];
    v40[1] = v14;
    v16 = CEseLayerPhysicalDatabase::CEseLayerPhysicalDatabase(v14, v40[0], a4);
    if ( v16 )
    {
      v17 = *v15;
      v37 = 0;
      v18 = CEseLayerPhysicalDatabase::Init(v16, a1, a2, v17, a6, a7, &v37);
      EseInstanceInternal = v18;
      if ( v37 )
      {
        CEseLayerPhysicalDatabase::Clear(v16);
        CEseLayerPhysicalDatabase::`scalar deleting destructor'(v16, v20);
        EseInstanceInternal = 0;
        v24 = 0;
        for ( i = 0; i < 2 && !v24; ++i )
        {
          v24 = DeleteFileW(a2);
          if ( !v24 )
          {
            LastError = GetLastError();
            EseInstanceInternal = LastError;
            if ( LastError > 0 )
              EseInstanceInternal = (unsigned __int16)LastError | 0x80070000;
            if ( (unsigned int)(EseInstanceInternal + 2147024894) <= 1 )
              goto LABEL_16;
            if ( EseInstanceInternal < 0 && i + 1 < 2 )
              Sleep(0xBB8u);
          }
        }
        if ( EseInstanceInternal >= 0 )
        {
LABEL_16:
          v9 = v39;
          v11 = v38;
          v27 = a6;
          EseInstanceInternal = CEseLayerPhysicalDatabase::AttachPhysicalDatabaseInternal(
                                  a1,
                                  a2,
                                  v38,
                                  a4,
                                  1,
                                  a6,
                                  v39,
                                  a8);
          goto LABEL_22;
        }
        if ( (byte_180113B13 & 8) != 0 )
          WPP_SF_SD(v22, v21, v23, (_DWORD)a2, EseInstanceInternal);
        v9 = v39;
      }
      else if ( v18 < 0 )
      {
        CEseLayerPhysicalDatabase::`scalar deleting destructor'(v16, v19);
      }
      else
      {
        if ( GetModuleFileNameW(0, Filename, 0x105u) )
        {
          if ( (BYTE3(xmmword_180113B20) & 8) != 0 )
          {
            CurrentProcessId = GetCurrentProcessId();
            WPP_SF_SdS(v31, v30, v32, (unsigned int)Filename, CurrentProcessId, (__int64)a2);
          }
          if ( (byte_180113DC6 & 1) != 0 )
          {
            v33 = GetCurrentProcessId();
            McTemplateU0zqz_EventWriteTransfer(v35, v34, (unsigned int)Filename, v33, (__int64)a2);
          }
        }
        else if ( (byte_180113B13 & 8) != 0 )
        {
          v36 = GetLastError();
          WPP_SF_d(539, 12, WPP_3e6685cde710395def8a3daa1fd65f2e_Traceguids, v36);
        }
        *a8 = v16;
      }
    }
    v11 = v38;
  }
  v27 = a6;
LABEL_22:
  if ( a5 && ErrorPointsToCorruption(EseInstanceInternal) )
  {
    DeleteCorruptFiles(a4);
    return (unsigned int)CEseLayerPhysicalDatabase::AttachPhysicalDatabaseInternal(a1, a2, v11, a4, 0, v27, v9, a8);
  }
  return (unsigned int)EseInstanceInternal;
}

```

## disassembly

```asm
0x1800433f4  push    rbx
0x1800433f6  push    rbp
0x1800433f7  push    rsi
0x1800433f8  push    rdi
0x1800433f9  push    r12
0x1800433fb  push    r13
0x1800433fd  push    r14
0x1800433ff  push    r15
0x180043401  sub     rsp, 298h
0x180043408  mov     rax, cs:__security_cookie
0x18004340f  xor     rax, rsp
0x180043412  mov     [rsp+2D8h+var_58], rax
0x18004341a  mov     r12, [rsp+2D8h+arg_38]
0x180043422  mov     r15d, r9d
0x180043425  mov     rbp, [rsp+2D8h+arg_30]
0x18004342d  mov     rsi, rdx
0x180043430  mov     r14, r8
0x180043433  mov     [rsp+2D8h+var_290], r8
0x180043438  mov     r13, rcx
0x18004343b  mov     [rsp+2D8h+var_2B8], r8; unsigned __int16 *
0x180043440  mov     rdx, rcx; unsigned __int16 *
0x180043443  mov     qword ptr [r12], 0
0x18004344b  mov     r9b, 1; bool
0x18004344e  mov     [rsp+2D8h+var_288], rbp
0x180043453  mov     r8d, r15d; unsigned int
0x180043456  mov     [rsp+2D8h+var_280], 0
0x18004345f  lea     rcx, [rsp+2D8h+var_280]; struct CEseInstance **
0x180043464  call    ?CreateEseInstanceInternal@CEseInstance@@CAJPEAPEAV1@PEBGK_N1@Z; CEseInstance::CreateEseInstanceInternal(CEseInstance * *,ushort const *,ulong,bool,ushort const *)
0x180043469  mov     ebx, eax
0x18004346b  test    eax, eax
0x18004346d  js      loc_1800435A8
0x180043473  mov     ecx, 288h; Size
0x180043478  mov     ebx, 8007000Eh
0x18004347d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180043482  mov     r14, [rsp+2D8h+var_280]
0x180043487  mov     r8d, r15d; unsigned int
0x18004348a  mov     rdx, r14; struct CEseInstance *
0x18004348d  mov     [rsp+2D8h+var_278], rax
0x180043492  mov     rcx, rax; this
0x180043495  call    ??0CEseLayerPhysicalDatabase@@AEAA@PEAVCEseInstance@@K@Z; CEseLayerPhysicalDatabase::CEseLayerPhysicalDatabase(CEseInstance *,ulong)
0x18004349a  mov     rdi, rax
0x18004349d  test    rax, rax
0x1800434a0  jz      loc_1800435A3
0x1800434a6  mov     r9, [r14]; unsigned __int64
0x1800434a9  lea     rax, [rsp+2D8h+var_298]
0x1800434ae  mov     [rsp+2D8h+var_2A8], rax; bool *
0x1800434b3  mov     r8, rsi; unsigned __int16 *
0x1800434b6  mov     eax, [rsp+2D8h+arg_28]
0x1800434bd  mov     rdx, r13; unsigned __int16 *
0x1800434c0  mov     [rsp+2D8h+var_2B0], rbp; unsigned __int16 *
0x1800434c5  mov     rcx, rdi; this
0x1800434c8  mov     dword ptr [rsp+2D8h+var_2B8], eax; unsigned int
0x1800434cc  mov     [rsp+2D8h+var_298], 0
0x1800434d1  call    ?Init@CEseLayerPhysicalDatabase@@QEAAJPEBG0_KKQEBGPEA_N@Z; CEseLayerPhysicalDatabase::Init(ushort const *,ushort const *,unsigned __int64,ulong,ushort const * const,bool *)
0x1800434d6  cmp     [rsp+2D8h+var_298], 0
0x1800434db  mov     ebx, eax
0x1800434dd  jz      loc_180043618
0x1800434e3  mov     rcx, rdi; this
0x1800434e6  call    ?Clear@CEseLayerPhysicalDatabase@@AEAAXXZ; CEseLayerPhysicalDatabase::Clear(void)
0x1800434eb  mov     rcx, rdi; this
0x1800434ee  call    ??_GCEseLayerPhysicalDatabase@@QEAAPEAXI@Z; CEseLayerPhysicalDatabase::`scalar deleting destructor'(uint)
0x1800434f3  xor     ebx, ebx
0x1800434f5  xor     ebp, ebp
0x1800434f7  xor     edi, edi
0x1800434f9  cmp     edi, 2
0x1800434fc  jnb     short loc_18004354C
0x1800434fe  test    ebp, ebp
0x180043500  jnz     short loc_18004354C
0x180043502  mov     rcx, rsi; lpFileName
0x180043505  call    cs:__imp_DeleteFileW
0x18004350b  mov     ebp, eax
0x18004350d  test    eax, eax
0x18004350f  jnz     short loc_180043548
0x180043511  call    cs:__imp_GetLastError
0x180043517  mov     ebx, eax
0x180043519  test    eax, eax
0x18004351b  jle     short loc_180043526
0x18004351d  movzx   ebx, ax
0x180043520  or      ebx, 80070000h
0x180043526  lea     eax, [rbx+7FF8FFFEh]
0x18004352c  cmp     eax, 1
0x18004352f  jbe     short loc_180043550
0x180043531  test    ebx, ebx
0x180043533  jns     short loc_180043548
0x180043535  lea     eax, [rdi+1]
0x180043538  cmp     eax, 2
0x18004353b  jnb     short loc_180043548
0x18004353d  mov     ecx, 0BB8h; dwMilliseconds
0x180043542  call    cs:__imp_Sleep
0x180043548  inc     edi
0x18004354a  jmp     short loc_1800434F9
0x18004354c  test    ebx, ebx
0x18004354e  js      short loc_180043589
0x180043550  mov     rbp, [rsp+2D8h+var_288]
0x180043555  mov     r9d, r15d; unsigned int
0x180043558  mov     r14, [rsp+2D8h+var_290]
0x18004355d  mov     rdx, rsi; unsigned __int16 *
0x180043560  mov     edi, [rsp+2D8h+arg_28]
0x180043567  mov     r8, r14; unsigned __int16 *
0x18004356a  mov     [rsp+2D8h+var_2A0], r12; struct CEseLayerPhysicalDatabase **
0x18004356f  mov     rcx, r13; unsigned __int16 *
0x180043572  mov     [rsp+2D8h+var_2A8], rbp; unsigned __int16 *
0x180043577  mov     dword ptr [rsp+2D8h+var_2B0], edi; unsigned int
0x18004357b  mov     byte ptr [rsp+2D8h+var_2B8], 1; bool
0x180043580  call    ?AttachPhysicalDatabaseInternal@CEseLayerPhysicalDatabase@@CAJPEBG00K_NKQEBGPEAPEAV1@@Z; CEseLayerPhysicalDatabase::AttachPhysicalDatabaseInternal(ushort const *,ushort const *,ushort const *,ulong,bool,ulong,ushort const * const,CEseLayerPhysicalDatabase * *)
0x180043585  mov     ebx, eax
0x180043587  jmp     short loc_1800435AF
0x180043589  test    cs:byte_180113B13, 8
0x180043590  jz      short loc_18004359E
0x180043592  mov     r9, rsi
0x180043595  mov     dword ptr [rsp+2D8h+var_2B8], ebx
0x180043599  call    WPP_SF_SD
0x18004359e  mov     rbp, [rsp+2D8h+var_288]
0x1800435a3  mov     r14, [rsp+2D8h+var_290]
0x1800435a8  mov     edi, [rsp+2D8h+arg_28]
0x1800435af  cmp     [rsp+2D8h+arg_20], 0
0x1800435b7  jz      short loc_1800435F2
0x1800435b9  mov     ecx, ebx; int
0x1800435bb  call    ?ErrorPointsToCorruption@@YA_NJ@Z; ErrorPointsToCorruption(long)
0x1800435c0  test    al, al
0x1800435c2  jz      short loc_1800435F2
0x1800435c4  mov     ecx, r15d; unsigned int
0x1800435c7  call    ?DeleteCorruptFiles@@YAJK@Z; DeleteCorruptFiles(ulong)
0x1800435cc  mov     [rsp+2D8h+var_2A0], r12; struct CEseLayerPhysicalDatabase **
0x1800435d1  mov     r9d, r15d; unsigned int
0x1800435d4  mov     [rsp+2D8h+var_2A8], rbp; unsigned __int16 *
0x1800435d9  mov     r8, r14; unsigned __int16 *
0x1800435dc  mov     dword ptr [rsp+2D8h+var_2B0], edi; unsigned int
0x1800435e0  mov     rdx, rsi; unsigned __int16 *
0x1800435e3  mov     rcx, r13; unsigned __int16 *
0x1800435e6  mov     byte ptr [rsp+2D8h+var_2B8], 0; bool
0x1800435eb  call    ?AttachPhysicalDatabaseInternal@CEseLayerPhysicalDatabase@@CAJPEBG00K_NKQEBGPEAPEAV1@@Z; CEseLayerPhysicalDatabase::AttachPhysicalDatabaseInternal(ushort const *,ushort const *,ushort const *,ulong,bool,ulong,ushort const * const,CEseLayerPhysicalDatabase * *)
0x1800435f0  mov     ebx, eax
0x1800435f2  mov     eax, ebx
0x1800435f4  mov     rcx, [rsp+2D8h+var_58]
0x1800435fc  xor     rcx, rsp; StackCookie
0x1800435ff  call    __security_check_cookie
0x180043604  add     rsp, 298h
0x18004360b  pop     r15
0x18004360d  pop     r14
0x18004360f  pop     r13
0x180043611  pop     r12
0x180043613  pop     rdi
0x180043614  pop     rsi
0x180043615  pop     rbp
0x180043616  pop     rbx
0x180043617  retn
0x180043618  test    eax, eax
0x18004361a  js      loc_1800436AD
0x180043620  mov     r8d, 105h; nSize
0x180043626  lea     rdx, [rsp+2D8h+Filename]; lpFilename
0x18004362b  xor     ecx, ecx; hModule
0x18004362d  call    cs:__imp_GetModuleFileNameW
0x180043633  test    eax, eax
0x180043635  jz      short loc_18004367C
0x180043637  test    byte ptr cs:xmmword_180113B20+3, 8
0x18004363e  jz      short loc_180043659
0x180043640  call    cs:__imp_GetCurrentProcessId
0x180043646  lea     r9, [rsp+2D8h+Filename]
0x18004364b  mov     [rsp+2D8h+var_2B0], rsi
0x180043650  mov     dword ptr [rsp+2D8h+var_2B8], eax
0x180043654  call    WPP_SF_SdS
0x180043659  test    cs:byte_180113DC6, 1
0x180043660  jz      short loc_1800436A4
0x180043662  call    cs:__imp_GetCurrentProcessId
0x180043668  lea     r8, [rsp+2D8h+Filename]
0x18004366d  mov     [rsp+2D8h+var_2B8], rsi
0x180043672  mov     r9d, eax
0x180043675  call    McTemplateU0zqz_EventWriteTransfer
0x18004367a  jmp     short loc_1800436A4
0x18004367c  test    cs:byte_180113B13, 8
0x180043683  jz      short loc_1800436A4
0x180043685  call    cs:__imp_GetLastError
0x18004368b  mov     edx, 0Ch
0x180043690  lea     r8, WPP_3e6685cde710395def8a3daa1fd65f2e_Traceguids
0x180043697  mov     r9d, eax
0x18004369a  mov     ecx, 21Bh
0x18004369f  call    WPP_SF_d
0x1800436a4  mov     [r12], rdi
0x1800436a8  jmp     loc_1800435A3
0x1800436ad  mov     rcx, rdi; this
0x1800436b0  call    ??_GCEseLayerPhysicalDatabase@@QEAAPEAXI@Z; CEseLayerPhysicalDatabase::`scalar deleting destructor'(uint)
0x1800436b5  jmp     loc_1800435A3
```
