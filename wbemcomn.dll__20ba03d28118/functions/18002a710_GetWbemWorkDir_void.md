# GetWbemWorkDir(void)

- ea: `0x18002a710`
- end: `0x18002a8cd`
- name: `?GetWbemWorkDir@@YAPEAGXZ`
- size: `445`
- prototype: `LPWSTR(void)`
- caller_count: `2`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002a560`
- `0x180042b80`

## callees

- `0x18000a290`
- `0x18000eea0`
- `0x18000f4c0`
- `0x18000f670`
- `0x18001016c`
- `0x180011e40`
- `0x180013564`
- `0x180014120`
- `0x1800298f0`
- `0x18002a710`
- `0x18002c98c`
- `0x180033f0c`
- `0x1800378f8`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18002a7b1`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18002a7fd`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18002a7b1`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18002a7fd`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18002a767`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18002a767`

## string_xrefs

- `0x18002a748`: `Working Directory`

## pseudocode

```c
LPWSTR GetWbemWorkDir(void)
{
  unsigned __int64 v0; // rsi
  void *v1; // rax
  unsigned __int16 *v2; // rbx
  UINT SystemDirectoryW; // eax
  UINT v4; // edi
  void *v5; // rax
  int v6; // eax
  unsigned int v7; // ebx
  LPWSTR v8; // rbx
  __int64 v10; // rcx
  __int64 v11; // [rsp+20h] [rbp-20h] BYREF
  __int64 v12; // [rsp+28h] [rbp-18h]
  LPWSTR lpBuffer; // [rsp+60h] [rbp+20h] BYREF

  lpBuffer = 0;
  Registry::Registry((Registry *)&v11, L"Software\\Microsoft\\WBEM\\CIMOM", 1u);
  if ( (unsigned int)Registry::GetStr((Registry *)&v11, L"Working Directory", &lpBuffer) )
  {
    v0 = lstrlenW(L"\\WBEM") + 261;
    v1 = CWin32DefaultArena::WbemMemAlloc(saturated_mul(v0, 2u));
    std::unique_ptr<CVarVector>::unique_ptr<CVarVector>(&lpBuffer, v1);
    v2 = lpBuffer;
    if ( !lpBuffer
      || (SystemDirectoryW = GetSystemDirectoryW(lpBuffer, 0x105u), (v4 = SystemDirectoryW) == 0)
      || SystemDirectoryW > 0x104
      && ((v0 = SystemDirectoryW + 5,
           v5 = CWin32DefaultArena::WbemMemAlloc(saturated_mul(v0, 2u)),
           std::unique_ptr<unsigned short [0]>::reset(&lpBuffer, v5),
           (v2 = lpBuffer) == 0)
       || !GetSystemDirectoryW(lpBuffer, v4 + 1)) )
    {
      std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(&lpBuffer);
      Registry::~Registry((Registry *)&v11);
      return 0;
    }
    v6 = StringCchCatW(v2, v0, L"\\WBEM");
    v7 = v6;
    if ( v6 < 0 )
    {
      CMemoryLog::Write((CMemoryLog *)qword_18006A9C0, v6);
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, WPP_a66c463c75c73635afca8e74831cc57c_Traceguids, v7);
      }
    }
    v8 = (LPWSTR)std::unique_ptr<CExecQueue::CThreadRecord>::release(&lpBuffer);
    std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(&lpBuffer);
  }
  else
  {
    v8 = lpBuffer;
  }
  v10 = v12;
  if ( v12 )
  {
    ((void (*)(void))DLRegCloseKey)();
    v10 = v12;
  }
  if ( v11 != v10 )
    DLRegCloseKey(v11);
  return v8;
}

```

## disassembly

```asm
0x18002a710  mov     [rsp-18h+arg_8], rbx
0x18002a715  mov     [rsp-18h+arg_10], rsi
0x18002a71a  push    rbp
0x18002a71b  push    rdi
0x18002a71c  push    r15
0x18002a71e  mov     rbp, rsp
0x18002a721  sub     rsp, 40h
0x18002a725  mov     [rbp+lpBuffer], 0
0x18002a72d  mov     r8d, 1; unsigned int
0x18002a733  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\WBEM\\CIMOM"
0x18002a73a  lea     rcx, [rbp+var_20]; this
0x18002a73e  call    ??0Registry@@QEAA@PEBGK@Z; Registry::Registry(ushort const *,ulong)
0x18002a743  nop
0x18002a744  lea     r8, [rbp+lpBuffer]; unsigned __int16 **
0x18002a748  lea     rdx, aWorkingDirecto; "Working Directory"
0x18002a74f  lea     rcx, [rbp+var_20]; this
0x18002a753  call    ?GetStr@Registry@@QEAAHPEBGPEAPEAG@Z; Registry::GetStr(ushort const *,ushort * *)
0x18002a758  test    eax, eax
0x18002a75a  jz      loc_18002A892
0x18002a760  lea     rcx, aWbem; "\\WBEM"
0x18002a767  call    cs:__imp_lstrlenW
0x18002a76d  mov     edi, 105h
0x18002a772  add     eax, edi
0x18002a774  movsxd  rsi, eax
0x18002a777  mov     eax, 2
0x18002a77c  mul     rsi
0x18002a77f  mov     r15, 0FFFFFFFFFFFFFFFFh
0x18002a786  cmovb   rax, r15
0x18002a78a  mov     rcx, rax; unsigned __int64
0x18002a78d  call    ?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18002a792  mov     rdx, rax
0x18002a795  lea     rcx, [rbp+lpBuffer]
0x18002a799  call    ??0?$unique_ptr@VCVarVector@@U?$default_delete@VCVarVector@@@std@@@std@@QEAA@PEAVCVarVector@@@Z; std::unique_ptr<CVarVector>::unique_ptr<CVarVector>(CVarVector *)
0x18002a79e  nop
0x18002a79f  mov     rbx, [rbp+lpBuffer]
0x18002a7a3  test    rbx, rbx
0x18002a7a6  jz      loc_18002A87B
0x18002a7ac  mov     edx, edi; uSize
0x18002a7ae  mov     rcx, rbx; lpBuffer
0x18002a7b1  call    cs:__imp_GetSystemDirectoryW
0x18002a7b7  mov     edi, eax
0x18002a7b9  test    eax, eax
0x18002a7bb  jz      loc_18002A87B
0x18002a7c1  cmp     eax, 104h
0x18002a7c6  jbe     short loc_18002A807
0x18002a7c8  lea     esi, [rax+5]
0x18002a7cb  lea     eax, [r15+3]
0x18002a7cf  mul     rsi
0x18002a7d2  cmovb   rax, r15
0x18002a7d6  mov     rcx, rax; unsigned __int64
0x18002a7d9  call    ?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18002a7de  mov     rdx, rax
0x18002a7e1  lea     rcx, [rbp+lpBuffer]
0x18002a7e5  call    ?reset@?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAAXPEAG@Z; std::unique_ptr<ushort [0]>::reset(ushort *)
0x18002a7ea  mov     rbx, [rbp+lpBuffer]
0x18002a7ee  test    rbx, rbx
0x18002a7f1  jz      loc_18002A87B
0x18002a7f7  lea     edx, [rdi+1]; uSize
0x18002a7fa  mov     rcx, rbx; lpBuffer
0x18002a7fd  call    cs:__imp_GetSystemDirectoryW
0x18002a803  test    eax, eax
0x18002a805  jz      short loc_18002A87B
0x18002a807  lea     r8, aWbem; "\\WBEM"
0x18002a80e  mov     rdx, rsi; unsigned __int64
0x18002a811  mov     rcx, rbx; unsigned __int16 *
0x18002a814  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002a819  mov     ebx, eax
0x18002a81b  test    eax, eax
0x18002a81d  jns     short loc_18002A864
0x18002a81f  mov     edx, eax; int
0x18002a821  lea     rcx, qword_18006A9C0; this
0x18002a828  call    ?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18002a82d  lea     rax, WPP_GLOBAL_Control
0x18002a834  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a83b  cmp     rcx, rax
0x18002a83e  jz      short loc_18002A864
0x18002a840  test    byte ptr [rcx+1Ch], 1
0x18002a844  jz      short loc_18002A864
0x18002a846  cmp     byte ptr [rcx+19h], 2
0x18002a84a  jb      short loc_18002A864
0x18002a84c  mov     edx, 1Bh
0x18002a851  mov     r9d, ebx
0x18002a854  lea     r8, WPP_a66c463c75c73635afca8e74831cc57c_Traceguids
0x18002a85b  mov     rcx, [rcx+10h]
0x18002a85f  call    WPP_SF_D
0x18002a864  lea     rcx, [rbp+lpBuffer]
0x18002a868  call    ?release@?$unique_ptr@VCThreadRecord@CExecQueue@@U?$default_delete@VCThreadRecord@CExecQueue@@@std@@@std@@QEAAPEAVCThreadRecord@CExecQueue@@XZ; std::unique_ptr<CExecQueue::CThreadRecord>::release(void)
0x18002a86d  mov     rbx, rax
0x18002a870  lea     rcx, [rbp+lpBuffer]
0x18002a874  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort [0]>::~unique_ptr<ushort [0]>(void)
0x18002a879  jmp     short loc_18002A896
0x18002a87b  lea     rcx, [rbp+lpBuffer]
0x18002a87f  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort [0]>::~unique_ptr<ushort [0]>(void)
0x18002a884  nop
0x18002a885  lea     rcx, [rbp+var_20]; this
0x18002a889  call    ??1Registry@@QEAA@XZ; Registry::~Registry(void)
0x18002a88e  xor     eax, eax
0x18002a890  jmp     short loc_18002A8BA
0x18002a892  mov     rbx, [rbp+lpBuffer]
0x18002a896  mov     rcx, [rbp+var_18]
0x18002a89a  test    rcx, rcx
0x18002a89d  jz      short loc_18002A8A8
0x18002a89f  call    DLRegCloseKey
0x18002a8a4  mov     rcx, [rbp+var_18]
0x18002a8a8  cmp     [rbp+var_20], rcx
0x18002a8ac  jz      short loc_18002A8B7
0x18002a8ae  mov     rcx, [rbp+var_20]
0x18002a8b2  call    DLRegCloseKey
0x18002a8b7  mov     rax, rbx
0x18002a8ba  mov     rbx, [rsp+40h+arg_8]
0x18002a8bf  mov     rsi, [rsp+40h+arg_10]
0x18002a8c4  add     rsp, 40h
0x18002a8c8  pop     r15
0x18002a8ca  pop     rdi
0x18002a8cb  pop     rbp
0x18002a8cc  retn
```
