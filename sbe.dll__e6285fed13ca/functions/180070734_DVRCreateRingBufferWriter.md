# DVRCreateRingBufferWriter

- ea: `0x180070734`
- end: `0x180070c27`
- name: `DVRCreateRingBufferWriter`
- size: `1267`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002bf8c`

## callees

- `0x1800017a0`
- `0x180001c00`
- `0x180068fd0`
- `0x180070734`
- `0x1800b6010`

## import_xrefs

- `KERNEL32!DuplicateHandle` at `0x180070993`
- `KERNEL32!DuplicateHandle` at `0x180070993`
- `KERNEL32!GetLastError` at `0x18007099d`
- `KERNEL32!GetLastError` at `0x18007099d`
- `KERNEL32!GetCurrentProcess` at `0x180070956`
- `KERNEL32!GetCurrentProcess` at `0x18007095f`
- `KERNEL32!GetCurrentProcess` at `0x180070956`
- `KERNEL32!GetCurrentProcess` at `0x18007095f`
- `ADVAPI32!RegCloseKey` at `0x180070bdd`
- `ADVAPI32!RegCloseKey` at `0x180070bf0`
- `ADVAPI32!RegCloseKey` at `0x1800b4b80`
- `ADVAPI32!RegCloseKey` at `0x1800b4b93`
- `ADVAPI32!RegCloseKey` at `0x180070bdd`
- `ADVAPI32!RegCloseKey` at `0x180070bf0`
- `ADVAPI32!RegCloseKey` at `0x1800b4b80`
- `ADVAPI32!RegCloseKey` at `0x1800b4b93`
- `ADVAPI32!RegCreateKeyExW` at `0x18007094e`
- `ADVAPI32!RegCreateKeyExW` at `0x1800709ff`
- `ADVAPI32!RegCreateKeyExW` at `0x18007094e`
- `ADVAPI32!RegCreateKeyExW` at `0x1800709ff`

## string_xrefs

- `0x1800709f8`: `IO\Writer`

## pseudocode

```c
__int64 __fastcall DVRCreateRingBufferWriter(
        struct CPVRIOCounters *a1,
        unsigned int a2,
        unsigned int a3,
        unsigned int a4,
        unsigned int a5,
        unsigned __int64 a6,
        struct IWMProfile *a7,
        unsigned int a8,
        unsigned int a9,
        int a10,
        unsigned int a11,
        unsigned int a12,
        unsigned int a13,
        unsigned int a14,
        __int64 a15,
        void *a16,
        void *a17,
        __int64 a18,
        WCHAR *lpFileName,
        unsigned int a20,
        void **a21,
        int a22,
        struct CPVRStreamProf *a23,
        int a24,
        _QWORD *a25)
{
  void **v28; // rbx
  CDVRRingBufferWriter *v29; // rdi
  int v30; // esi
  HANDLE CurrentProcess; // rbx
  HANDLE v32; // rax
  signed int LastError; // eax
  CDVRRingBufferWriter *v34; // r10
  __int64 v35; // rax
  size_t Size; // [rsp+B8h] [rbp-100h]
  HKEY hKey; // [rsp+160h] [rbp-58h] BYREF
  HKEY phkResult; // [rsp+168h] [rbp-50h] BYREF
  int v41; // [rsp+170h] [rbp-48h] BYREF

  v28 = a21;
  if ( !a25 || a2 <= 3 || a2 > a3 || a4 < a3 || a4 > 0xFFFE || a8 != -1 && !a9 )
    return 2147942487LL;
  if ( a20 )
  {
    if ( a21 )
      goto LABEL_12;
    return 2147942487LL;
  }
  if ( a21 )
    return 2147942487LL;
LABEL_12:
  v41 = 0;
  v29 = 0;
  phkResult = 0;
  hKey = 0;
  v30 = 1;
  *a25 = 0;
  if ( a17 )
  {
    CurrentProcess = GetCurrentProcess();
    v32 = GetCurrentProcess();
    if ( !DuplicateHandle(v32, a17, CurrentProcess, (LPHANDLE)&hKey, 0, 0, 2u) )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      goto LABEL_27;
    }
    v28 = a21;
  }
  else
  {
    RegCreateKeyExW(HKEY_CURRENT_USER, L"Software\\Microsoft\\DVR", 0, 0, 0, 0x2001Fu, 0, &hKey, 0);
  }
  v29 = 0;
  if ( hKey )
    RegCreateKeyExW(hKey, L"IO\\Writer", 0, 0, 0, 0x2001Fu, 0, &phkResult, 0);
  v34 = (CDVRRingBufferWriter *)operator new(0x268u);
  if ( v34 )
  {
    LODWORD(Size) = a22;
    v29 = CDVRRingBufferWriter::CDVRRingBufferWriter(
            v34,
            a1,
            a2,
            a3,
            a4,
            a5,
            a6,
            a7,
            a8,
            a9,
            a10,
            a11,
            a12,
            a13,
            a14,
            (void (*)(void *, unsigned int, __int64, __int64))CDVREventSink::DVRIOCallback,
            a16,
            hKey,
            phkResult,
            0,
            lpFileName,
            a20,
            v28,
            Size,
            a23,
            a24,
            &v41);
  }
  if ( v29 )
  {
    v30 = 0;
    v35 = *(_QWORD *)v29;
    if ( v41 < 0 )
    {
      (*(void (__fastcall **)(CDVRRingBufferWriter *))(v35 + 8))(v29);
      goto LABEL_28;
    }
    LastError = (*(__int64 (__fastcall **)(CDVRRingBufferWriter *, GUID *, _QWORD *))v35)(
                  v29,
                  &IID_IDVRRingBufferWriter,
                  a25);
LABEL_27:
    v41 = LastError;
    goto LABEL_28;
  }
  v41 = -2147024882;
LABEL_28:
  if ( v41 < 0 )
  {
    if ( v29 )
      (*(void (__fastcall **)(CDVRRingBufferWriter *, __int64))(*(_QWORD *)v29 + 128LL))(v29, 1);
    if ( v30 )
    {
      if ( phkResult )
        RegCloseKey(phkResult);
      if ( hKey )
        RegCloseKey(hKey);
    }
  }
  return (unsigned int)v41;
}

```

## disassembly

```asm
0x180070734  push    rbx
0x180070736  push    rsi
0x180070737  push    rdi
0x180070738  push    r12
0x18007073a  push    r13
0x18007073c  push    r14
0x18007073e  push    r15
0x180070740  sub     rsp, 180h
0x180070747  mov     rax, cs:__security_cookie
0x18007074e  xor     rax, rsp
0x180070751  mov     [rsp+1B8h+var_40], rax
0x180070759  mov     r12d, r9d
0x18007075c  mov     r15d, r8d
0x18007075f  mov     r14d, edx
0x180070762  mov     [rsp+1B8h+var_68], rcx
0x18007076a  mov     eax, [rsp+1B8h+arg_20]
0x180070771  mov     [rsp+1B8h+var_B0], eax
0x180070778  mov     rax, [rsp+1B8h+arg_28]
0x180070780  mov     [rsp+1B8h+var_70], rax
0x180070788  mov     rax, [rsp+1B8h+arg_30]
0x180070790  mov     [rsp+1B8h+var_78], rax
0x180070798  mov     edx, [rsp+1B8h+arg_38]
0x18007079f  mov     [rsp+1B8h+var_B4], edx
0x1800707a6  mov     r8d, [rsp+1B8h+arg_40]
0x1800707ae  mov     [rsp+1B8h+var_B8], r8d
0x1800707b6  mov     eax, [rsp+1B8h+arg_48]
0x1800707bd  mov     [rsp+1B8h+var_BC], eax
0x1800707c4  mov     eax, [rsp+1B8h+arg_50]
0x1800707cb  mov     [rsp+1B8h+var_C0], eax
0x1800707d2  mov     eax, [rsp+1B8h+arg_58]
0x1800707d9  mov     [rsp+1B8h+var_C4], eax
0x1800707e0  mov     eax, [rsp+1B8h+arg_60]
0x1800707e7  mov     [rsp+1B8h+var_C8], eax
0x1800707ee  mov     eax, [rsp+1B8h+arg_68]
0x1800707f5  mov     dword ptr [rsp+1B8h+var_D0+4], eax
0x1800707fc  mov     rax, [rsp+1B8h+arg_78]
0x180070804  mov     [rsp+1B8h+var_80], rax
0x18007080c  mov     rax, [rsp+1B8h+arg_80]
0x180070814  mov     [rsp+1B8h+hSourceHandle], rax
0x18007081c  mov     rcx, [rsp+1B8h+arg_90]
0x180070824  mov     [rsp+1B8h+var_88], rcx
0x18007082c  mov     r13d, [rsp+1B8h+arg_98]
0x180070834  mov     rbx, [rsp+1B8h+arg_A0]
0x18007083c  mov     [rsp+1B8h+var_98], rbx
0x180070844  mov     ecx, [rsp+1B8h+arg_A8]
0x18007084b  mov     dword ptr [rsp+1B8h+var_D0], ecx
0x180070852  mov     rcx, [rsp+1B8h+arg_B0]
0x18007085a  mov     [rsp+1B8h+var_90], rcx
0x180070862  mov     ecx, [rsp+1B8h+arg_B8]
0x180070869  mov     [rsp+1B8h+var_D4], ecx
0x180070870  mov     rcx, [rsp+1B8h+arg_C0]
0x180070878  mov     [rsp+1B8h+var_60], rcx
0x180070880  xor     r9d, r9d
0x180070883  test    rcx, rcx
0x180070886  jz      loc_180070BFF
0x18007088c  cmp     r14d, 3
0x180070890  jbe     loc_180070BFF
0x180070896  cmp     r14d, r15d
0x180070899  ja      loc_180070BFF
0x18007089f  cmp     r12d, r15d
0x1800708a2  jb      loc_180070BFF
0x1800708a8  cmp     r12d, 0FFFEh
0x1800708af  ja      loc_180070BFF
0x1800708b5  cmp     edx, 0FFFFFFFFh
0x1800708b8  jz      short loc_1800708C3
0x1800708ba  test    r8d, r8d
0x1800708bd  jz      loc_180070BFF
0x1800708c3  test    r13d, r13d
0x1800708c6  jnz     short loc_1800708D6
0x1800708c8  test    rbx, rbx
0x1800708cb  jnz     loc_180070BFF
0x1800708d1  test    r13d, r13d
0x1800708d4  jz      short loc_1800708DF
0x1800708d6  test    rbx, rbx
0x1800708d9  jz      loc_180070BFF
0x1800708df  mov     [rsp+1B8h+var_48], r9d
0x1800708e7  mov     rdi, r9
0x1800708ea  mov     [rsp+1B8h+var_A8], r9
0x1800708f2  mov     [rsp+1B8h+var_50], r9
0x1800708fa  mov     [rsp+1B8h+hKey], r9
0x180070902  mov     esi, 1
0x180070907  mov     [rsp+1B8h+var_D8], esi
0x18007090e  mov     [rcx], r9
0x180070911  test    rax, rax
0x180070914  jnz     short loc_180070956
0x180070916  mov     [rsp+1B8h+lpdwDisposition], r9; lpdwDisposition
0x18007091b  lea     rax, [rsp+1B8h+hKey]
0x180070923  mov     [rsp+1B8h+phkResult], rax; phkResult
0x180070928  mov     [rsp+1B8h+lpSecurityAttributes], r9; lpSecurityAttributes
0x18007092d  mov     [rsp+1B8h+samDesired], 2001Fh; samDesired
0x180070935  mov     [rsp+1B8h+dwOptions], r9d; dwOptions
0x18007093a  xor     r9d, r9d; lpClass
0x18007093d  xor     r8d, r8d; Reserved
0x180070940  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\DVR"
0x180070947  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18007094e  call    cs:__imp_RegCreateKeyExW
0x180070954  jmp     short loc_1800709C0
0x180070956  call    cs:__imp_GetCurrentProcess
0x18007095c  mov     rbx, rax
0x18007095f  call    cs:__imp_GetCurrentProcess
0x180070965  mov     dword ptr [rsp+1B8h+lpSecurityAttributes], 2; dwOptions
0x18007096d  mov     [rsp+1B8h+samDesired], 0; bInheritHandle
0x180070975  mov     [rsp+1B8h+dwOptions], 0; dwDesiredAccess
0x18007097d  lea     r9, [rsp+1B8h+hKey]; lpTargetHandle
0x180070985  mov     r8, rbx; hTargetProcessHandle
0x180070988  mov     rdx, [rsp+1B8h+hSourceHandle]; hSourceHandle
0x180070990  mov     rcx, rax; hSourceProcessHandle
0x180070993  call    cs:__imp_DuplicateHandle
0x180070999  test    eax, eax
0x18007099b  jnz     short loc_1800709B8
0x18007099d  call    cs:__imp_GetLastError
0x1800709a3  test    eax, eax
0x1800709a5  jle     loc_180070B9F
0x1800709ab  movzx   eax, ax
0x1800709ae  or      eax, 80070000h
0x1800709b3  jmp     loc_180070B9F
0x1800709b8  mov     rbx, [rsp+1B8h+var_98]
0x1800709c0  mov     rcx, [rsp+1B8h+hKey]; hKey
0x1800709c8  xor     edi, edi
0x1800709ca  test    rcx, rcx
0x1800709cd  jz      short loc_180070A05
0x1800709cf  mov     [rsp+1B8h+lpdwDisposition], rdi; lpdwDisposition
0x1800709d4  lea     rax, [rsp+1B8h+var_50]
0x1800709dc  mov     [rsp+1B8h+phkResult], rax; phkResult
0x1800709e1  mov     [rsp+1B8h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x1800709e6  mov     [rsp+1B8h+samDesired], 2001Fh; samDesired
0x1800709ee  mov     [rsp+1B8h+dwOptions], edi; dwOptions
0x1800709f2  xor     r9d, r9d; lpClass
0x1800709f5  xor     r8d, r8d; Reserved
0x1800709f8  lea     rdx, aIoWriter; "IO\\Writer"
0x1800709ff  call    cs:__imp_RegCreateKeyExW
0x180070a05  mov     ecx, 268h; Size
0x180070a0a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180070a0f  mov     r10, rax
0x180070a12  test    rax, rax
0x180070a15  jz      loc_180070B4B
0x180070a1b  lea     rax, [rsp+1B8h+var_48]
0x180070a23  mov     [rsp+1B8h+var_E8], rax; int *
0x180070a2b  mov     eax, [rsp+1B8h+var_D4]
0x180070a32  mov     [rsp+1B8h+var_F0], eax; int
0x180070a39  mov     rax, [rsp+1B8h+var_90]
0x180070a41  mov     [rsp+1B8h+var_F8], rax; struct CPVRStreamProf *
0x180070a49  mov     eax, dword ptr [rsp+1B8h+var_D0]
0x180070a50  mov     dword ptr [rsp+1B8h+Size], eax; Size
0x180070a57  mov     [rsp+1B8h+var_108], rbx; void **
0x180070a5f  mov     [rsp+1B8h+var_110], r13d; unsigned int
0x180070a67  mov     rax, [rsp+1B8h+var_88]
0x180070a6f  mov     [rsp+1B8h+lpFileName], rax; lpFileName
0x180070a77  mov     [rsp+1B8h+var_120], rdi; unsigned __int16 *
0x180070a7f  mov     rcx, [rsp+1B8h+var_50]
0x180070a87  mov     [rsp+1B8h+var_128], rcx; HKEY
0x180070a8f  mov     rax, [rsp+1B8h+hKey]
0x180070a97  mov     [rsp+1B8h+var_130], rax; HKEY
0x180070a9f  mov     rax, [rsp+1B8h+var_80]
0x180070aa7  mov     [rsp+1B8h+var_138], rax; void *
0x180070aaf  lea     rax, ?DVRIOCallback@CDVREventSink@@SAXPEAXK_J1@Z; CDVREventSink::DVRIOCallback(void *,ulong,__int64,__int64)
0x180070ab6  mov     [rsp+1B8h+var_140], rax; void (*)(void *, unsigned int, __int64, __int64)
0x180070abb  mov     eax, dword ptr [rsp+1B8h+var_D0+4]
0x180070ac2  mov     [rsp+1B8h+var_148], eax; unsigned int
0x180070ac6  mov     eax, [rsp+1B8h+var_C8]
0x180070acd  mov     [rsp+1B8h+var_150], eax; unsigned int
0x180070ad1  mov     eax, [rsp+1B8h+var_C4]
0x180070ad8  mov     [rsp+1B8h+var_158], eax; unsigned int
0x180070adc  mov     eax, [rsp+1B8h+var_C0]
0x180070ae3  mov     [rsp+1B8h+var_160], eax; unsigned int
0x180070ae7  mov     eax, [rsp+1B8h+var_BC]
0x180070aee  mov     [rsp+1B8h+var_168], eax; int
0x180070af2  mov     eax, [rsp+1B8h+var_B8]
0x180070af9  mov     [rsp+1B8h+var_170], eax; unsigned int
0x180070afd  mov     eax, [rsp+1B8h+var_B4]
0x180070b04  mov     dword ptr [rsp+1B8h+lpdwDisposition], eax; unsigned int
0x180070b08  mov     rax, [rsp+1B8h+var_78]
0x180070b10  mov     [rsp+1B8h+phkResult], rax; struct IWMProfile *
0x180070b15  mov     rax, [rsp+1B8h+var_70]
0x180070b1d  mov     [rsp+1B8h+lpSecurityAttributes], rax; unsigned __int64
0x180070b22  mov     eax, [rsp+1B8h+var_B0]
0x180070b29  mov     [rsp+1B8h+samDesired], eax; unsigned int
0x180070b2d  mov     [rsp+1B8h+dwOptions], r12d; unsigned int
0x180070b32  mov     r9d, r15d; unsigned int
0x180070b35  mov     r8d, r14d; unsigned int
0x180070b38  mov     rdx, [rsp+1B8h+var_68]; struct CPVRIOCounters *
0x180070b40  mov     rcx, r10; this
0x180070b43  call    ??0CDVRRingBufferWriter@@QEAA@PEAVCPVRIOCounters@@KKKK_KPEAUIWMProfile@@KKHKKKKP6AXPEAXK_J4@Z3PEAUHKEY__@@6PEBG7KPEAPEAXKAEAVCPVRStreamProf@@HPEAJ@Z; CDVRRingBufferWriter::CDVRRingBufferWriter(CPVRIOCounters *,ulong,ulong,ulong,ulong,unsigned __int64,IWMProfile *,ulong,ulong,int,ulong,ulong,ulong,ulong,void (*)(void *,ulong,__int64,__int64),void *,HKEY__ *,HKEY__ *,ushort const *,ushort const *,ulong,void * *,ulong,CPVRStreamProf &,int,long *)
0x180070b48  mov     rdi, rax
0x180070b4b  mov     [rsp+1B8h+var_A8], rdi
0x180070b53  test    rdi, rdi
0x180070b56  jnz     short loc_180070B65
0x180070b58  mov     [rsp+1B8h+var_48], 8007000Eh
0x180070b63  jmp     short loc_180070BA6
0x180070b65  xor     esi, esi
0x180070b67  mov     [rsp+1B8h+var_D8], esi
0x180070b6e  mov     rax, [rdi]
0x180070b71  mov     rcx, rdi
0x180070b74  cmp     [rsp+1B8h+var_48], esi
0x180070b7b  jge     short loc_180070B88
0x180070b7d  mov     rax, [rax+8]
0x180070b81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180070b86  jmp     short loc_180070BA6
0x180070b88  mov     r8, [rsp+1B8h+var_60]
0x180070b90  lea     rdx, IID_IDVRRingBufferWriter
0x180070b97  mov     rax, [rax]
0x180070b9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180070b9f  mov     [rsp+1B8h+var_48], eax
0x180070ba6  cmp     [rsp+1B8h+var_48], 0
0x180070bae  jge     short loc_180070BF6
0x180070bb0  test    rdi, rdi
0x180070bb3  jz      short loc_180070BCC
0x180070bb5  mov     rax, [rdi]
0x180070bb8  mov     edx, 1
0x180070bbd  mov     rcx, rdi
0x180070bc0  mov     rax, [rax+80h]
0x180070bc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180070bcc  test    esi, esi
0x180070bce  jz      short loc_180070BF6
0x180070bd0  mov     rcx, [rsp+1B8h+var_50]; hKey
0x180070bd8  test    rcx, rcx
0x180070bdb  jz      short loc_180070BE3
0x180070bdd  call    cs:__imp_RegCloseKey
0x180070be3  mov     rcx, [rsp+1B8h+hKey]; hKey
0x180070beb  test    rcx, rcx
0x180070bee  jz      short loc_180070BF6
0x180070bf0  call    cs:__imp_RegCloseKey
0x180070bf6  mov     eax, [rsp+1B8h+var_48]
0x180070bfd  jmp     short loc_180070C04
0x180070bff  mov     eax, 80070057h
0x180070c04  mov     rcx, [rsp+1B8h+var_40]
0x180070c0c  xor     rcx, rsp; StackCookie
0x180070c0f  call    __security_check_cookie
0x180070c14  add     rsp, 180h
0x180070c1b  pop     r15
0x180070c1d  pop     r14
0x180070c1f  pop     r13
0x180070c21  pop     r12
0x180070c23  pop     rdi
0x180070c24  pop     rsi
0x180070c25  pop     rbx
0x180070c26  retn
0x1800b4b35  push    rbp
0x1800b4b37  sub     rsp, 0E0h
0x1800b4b3e  mov     rbp, rdx
0x1800b4b41  cmp     dword ptr [rbp+170h], 0
0x1800b4b48  jge     short loc_1800B4B9A
0x1800b4b4a  mov     rcx, [rbp+110h]
0x1800b4b51  test    rcx, rcx
0x1800b4b54  jz      short loc_1800B4B6B
0x1800b4b56  mov     rax, [rcx]
0x1800b4b59  mov     edx, 1
0x1800b4b5e  mov     rax, [rax+80h]
0x1800b4b65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b4b6a  nop
0x1800b4b6b  cmp     dword ptr [rbp+0E0h], 0
0x1800b4b72  jz      short loc_1800B4B9A
0x1800b4b74  mov     rcx, [rbp+168h]; hKey
0x1800b4b7b  test    rcx, rcx
0x1800b4b7e  jz      short loc_1800B4B87
0x1800b4b80  call    cs:__imp_RegCloseKey
0x1800b4b86  nop
0x1800b4b87  mov     rcx, [rbp+160h]; hKey
0x1800b4b8e  test    rcx, rcx
0x1800b4b91  jz      short loc_1800B4B9A
0x1800b4b93  call    cs:__imp_RegCloseKey
0x1800b4b99  nop
0x1800b4b9a  add     rsp, 0E0h
0x1800b4ba1  pop     rbp
0x1800b4ba2  retn
```
