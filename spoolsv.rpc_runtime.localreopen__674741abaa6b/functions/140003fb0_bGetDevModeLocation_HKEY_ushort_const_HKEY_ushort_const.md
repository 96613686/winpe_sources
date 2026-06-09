# bGetDevModeLocation(HKEY__ *,ushort const *,HKEY__ * *,ushort const * *)

- ea: `0x140003fb0`
- end: `0x1400042dc`
- name: `?bGetDevModeLocation@@YAHPEAUHKEY__@@PEBGPEAPEAU1@PEAPEBG@Z`
- size: `812`
- prototype: `__int64 __fastcall(HKEY hKey, const unsigned __int16 *, PHKEY phkResult, const unsigned __int16 **)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x140011770`
- `0x140018bc0`

## callees

- `0x140003fb0`
- `0x140004790`
- `0x140004800`
- `0x14000d450`
- `0x140015378`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140004223`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140004223`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400040f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004153`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400042a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400040f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004153`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400042a0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140004236`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140004250`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140004236`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140004250`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140004209`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140004209`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x14000408f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x14000408f`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x1400040c2`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x1400040c2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000400f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140004284`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000400f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140004284`

## string_xrefs

- `0x140004264`: `RegOpenCurrentUser failed. Error %d.`

## pseudocode

```c
__int64 __fastcall bGetDevModeLocation(
        HKEY hKey,
        const unsigned __int16 *a2,
        PHKEY phkResult,
        const unsigned __int16 **a4)
{
  HKEY ClientUserHandle; // r14
  HKEY v8; // rbx
  DWORD LastError; // esi
  LSTATUS v11; // eax
  unsigned int v12; // ebx
  unsigned __int64 v13; // rax
  __int64 v14; // rax
  WCHAR *v15; // r13
  __int64 v16; // rcx
  const unsigned __int16 *v17; // r9
  __int64 v18; // r8
  _WORD *v19; // rdx
  _WORD *v20; // rcx
  __int64 v21; // r10
  unsigned __int16 i; // ax
  DWORD dwDisposition; // [rsp+90h] [rbp+8h] BYREF
  HKEY hKeya; // [rsp+A0h] [rbp+18h] BYREF

  ClientUserHandle = hKey;
  *phkResult = 0;
  v8 = 0;
  *a4 = 0;
  if ( !hKey )
  {
    hKeya = 0;
    v11 = RegOpenCurrentUser(0x2001Fu, &hKeya);
    v12 = v11;
    if ( v11 )
    {
      SetLastError(v11);
      if ( v12 != 5 )
        PrvSpoolssTelemetry::WriteDbgTraceError("SplGetClientUserHandle", L"RegOpenCurrentUser failed. Error %d.", v12);
      if ( hKeya )
        RegCloseKey(hKeya);
      ClientUserHandle = 0;
      hKeya = 0;
    }
    else
    {
      ClientUserHandle = hKeya;
    }
    if ( !ClientUserHandle && GetLastError() == 5 )
      ClientUserHandle = (HKEY)SplGetClientUserHandle(131097);
    v8 = ClientUserHandle;
    if ( !ClientUserHandle )
    {
      LastError = GetLastError();
      goto LABEL_6;
    }
  }
  LastError = 0;
  if ( *a2 != 92 || a2[1] != 92 )
    goto LABEL_3;
  v13 = -1;
  do
    ++v13;
  while ( a2[v13] );
  if ( v13 >= 0x21B )
  {
    LastError = 87;
LABEL_3:
    if ( !*a4 )
    {
      dwDisposition = 0;
      LastError = RegCreateKeyExW(
                    ClientUserHandle,
                    L"Printers\\DevModePerUser",
                    0,
                    0,
                    0,
                    0x2001Fu,
                    0,
                    phkResult,
                    &dwDisposition);
      if ( !LastError )
        *a4 = a2;
    }
    goto LABEL_4;
  }
  v14 = DllAllocSplMem(0x462u);
  v15 = (WCHAR *)v14;
  if ( v14 )
  {
    v16 = 2147483646;
    v17 = L"Printers\\Connections\\";
    v18 = 561;
    v19 = (_WORD *)v14;
    do
    {
      if ( !v16 )
        break;
      if ( !*v17 )
        break;
      *v19++ = *v17++;
      --v16;
      --v18;
    }
    while ( v18 );
    v20 = v19 - 1;
    v21 = v14 + 42;
    if ( v18 )
      v20 = v19;
    *v20 = 0;
    if ( (const unsigned __int16 *)v21 != a2 )
      StringCchCopyW((unsigned __int16 *)(v14 + 42), 0x21Cu, a2);
    for ( i = *(_WORD *)v21; i; v21 += 2 )
    {
      if ( i == 92 )
        *(_WORD *)v21 = 44;
      i = *(_WORD *)(v21 + 2);
    }
    LastError = RegOpenKeyExW(ClientUserHandle, v15, 0, 0x2001Fu, phkResult);
    HeapFree(g_hSpoolssHeap, 0, v15);
  }
  else
  {
    LastError = GetLastError();
  }
  if ( LastError )
    goto LABEL_3;
  *a4 = L"DevMode";
LABEL_4:
  if ( v8 )
    RegCloseKey(v8);
LABEL_6:
  if ( !LastError )
    return 1;
  SetLastError(LastError);
  return 0;
}

```

## disassembly

```asm
0x140003fb0  mov     rax, rsp
0x140003fb3  push    rsi
0x140003fb4  sub     rsp, 80h
0x140003fbb  mov     [rax+10h], rbx
0x140003fbf  mov     [rax-10h], rbp
0x140003fc3  mov     rbp, rdx
0x140003fc6  mov     [rax-18h], rdi
0x140003fca  mov     rdi, r9
0x140003fcd  mov     [rax-20h], r12
0x140003fd1  xor     r12d, r12d
0x140003fd4  mov     [rax-30h], r14
0x140003fd8  mov     r14, rcx
0x140003fdb  mov     [rax-38h], r15
0x140003fdf  mov     r15, r8
0x140003fe2  mov     [r8], r12
0x140003fe5  mov     ebx, r12d
0x140003fe8  mov     [r9], r12
0x140003feb  test    rcx, rcx
0x140003fee  jz      loc_1400040AD
0x140003ff4  cmp     word ptr [rbp+0], 5Ch ; '\'
0x140003ff9  mov     esi, r12d
0x140003ffc  jz      loc_140004108
0x140004002  cmp     [rdi], r12
0x140004005  jz      short loc_140004053
0x140004007  test    rbx, rbx
0x14000400a  jz      short loc_14000401B
0x14000400c  mov     rcx, rbx; hKey
0x14000400f  call    cs:__imp_RegCloseKey
0x140004016  nop     dword ptr [rax+rax+00h]
0x14000401b  mov     r15, [rsp+88h+var_38]
0x140004020  mov     r14, [rsp+88h+var_30]
0x140004025  mov     r12, [rsp+88h+var_20]
0x14000402a  mov     rdi, [rsp+88h+var_18]
0x14000402f  mov     rbp, [rsp+88h+var_10]
0x140004034  mov     rbx, [rsp+88h+arg_8]
0x14000403c  test    esi, esi
0x14000403e  jnz     loc_140004234
0x140004044  mov     eax, 1
0x140004049  add     rsp, 80h
0x140004050  pop     rsi
0x140004051  retn
0x140004053  lea     rax, [rsp+88h+dwDisposition]
0x14000405b  mov     [rsp+88h+dwDisposition], r12d
0x140004063  mov     [rsp+88h+lpdwDisposition], rax; lpdwDisposition
0x140004068  lea     rdx, gszDevModePerUserLocal; "Printers\\DevModePerUser"
0x14000406f  mov     [rsp+88h+phkResult], r15; phkResult
0x140004074  xor     r9d, r9d; lpClass
0x140004077  mov     [rsp+88h+lpSecurityAttributes], r12; lpSecurityAttributes
0x14000407c  xor     r8d, r8d; Reserved
0x14000407f  mov     [rsp+88h+samDesired], 2001Fh; samDesired
0x140004087  mov     rcx, r14; hKey
0x14000408a  mov     [rsp+88h+dwOptions], r12d; dwOptions
0x14000408f  call    cs:__imp_RegCreateKeyExW
0x140004096  nop     dword ptr [rax+rax+00h]
0x14000409b  mov     esi, eax
0x14000409d  test    eax, eax
0x14000409f  jnz     loc_140004007
0x1400040a5  mov     [rdi], rbp
0x1400040a8  jmp     loc_140004007
0x1400040ad  lea     rdx, [rsp+88h+hKey]; phkResult
0x1400040b5  mov     [rsp+88h+hKey], r12
0x1400040bd  mov     ecx, 2001Fh; samDesired
0x1400040c2  call    cs:__imp_RegOpenCurrentUser
0x1400040c9  nop     dword ptr [rax+rax+00h]
0x1400040ce  mov     ebx, eax
0x1400040d0  test    eax, eax
0x1400040d2  jnz     loc_14000424E
0x1400040d8  mov     r14, [rsp+88h+hKey]
0x1400040e0  test    r14, r14
0x1400040e3  jz      loc_1400042A0
0x1400040e9  mov     rbx, r14
0x1400040ec  test    r14, r14
0x1400040ef  jnz     loc_140003FF4
0x1400040f5  call    cs:__imp_GetLastError
0x1400040fc  nop     dword ptr [rax+rax+00h]
0x140004101  mov     esi, eax
0x140004103  jmp     loc_14000401B
0x140004108  cmp     word ptr [rbp+2], 5Ch ; '\'
0x14000410d  jnz     loc_140004002
0x140004113  mov     rax, 0FFFFFFFFFFFFFFFFh
0x14000411a  nop     word ptr [rax+rax+00h]
0x140004120  inc     rax
0x140004123  cmp     [rbp+rax*2+0], si
0x140004128  jnz     short loc_140004120
0x14000412a  cmp     rax, 21Bh
0x140004130  jb      short loc_14000413C
0x140004132  mov     esi, 57h ; 'W'
0x140004137  jmp     loc_140004002
0x14000413c  mov     ecx, 462h; dwBytes
0x140004141  mov     [rsp+88h+var_28], r13
0x140004146  call    DllAllocSplMem
0x14000414b  mov     r13, rax
0x14000414e  test    rax, rax
0x140004151  jnz     short loc_14000417D
0x140004153  call    cs:__imp_GetLastError
0x14000415a  nop     dword ptr [rax+rax+00h]
0x14000415f  mov     esi, eax
0x140004161  mov     r13, [rsp+88h+var_28]
0x140004166  test    esi, esi
0x140004168  jnz     loc_140004002
0x14000416e  lea     rax, gszDevMode; "DevMode"
0x140004175  mov     [rdi], rax
0x140004178  jmp     loc_140004007
0x14000417d  mov     ecx, 7FFFFFFEh
0x140004182  lea     r9, gszPrinterConnections; "Printers\\Connections\\"
0x140004189  mov     r8d, 231h
0x14000418f  mov     rdx, r13
0x140004192  test    rcx, rcx
0x140004195  jz      short loc_1400041B6
0x140004197  movzx   r10d, word ptr [r9]
0x14000419b  test    r10w, r10w
0x14000419f  jz      short loc_1400041B6
0x1400041a1  mov     [rdx], r10w
0x1400041a5  add     r9, 2
0x1400041a9  add     rdx, 2
0x1400041ad  dec     rcx
0x1400041b0  sub     r8, 1
0x1400041b4  jnz     short loc_140004192
0x1400041b6  test    r8, r8
0x1400041b9  lea     rcx, [rdx-2]
0x1400041bd  lea     r10, [rax+2Ah]
0x1400041c1  cmovnz  rcx, rdx
0x1400041c5  mov     [rcx], r12w
0x1400041c9  cmp     r10, rbp
0x1400041cc  jnz     loc_1400042C7
0x1400041d2  movzx   eax, word ptr [r10]
0x1400041d6  test    ax, ax
0x1400041d9  jz      short loc_1400041F5
0x1400041db  cmp     ax, 5Ch ; '\'
0x1400041df  jnz     short loc_1400041E7
0x1400041e1  mov     word ptr [r10], 2Ch ; ','
0x1400041e7  movzx   eax, word ptr [r10+2]
0x1400041ec  add     r10, 2
0x1400041f0  test    ax, ax
0x1400041f3  jnz     short loc_1400041DB
0x1400041f5  mov     r9d, 2001Fh; samDesired
0x1400041fb  mov     qword ptr [rsp+88h+dwOptions], r15; phkResult
0x140004200  xor     r8d, r8d; ulOptions
0x140004203  mov     rdx, r13; lpSubKey
0x140004206  mov     rcx, r14; hKey
0x140004209  call    cs:__imp_RegOpenKeyExW
0x140004210  nop     dword ptr [rax+rax+00h]
0x140004215  mov     rcx, cs:?g_hSpoolssHeap@@3PEAXEA; hHeap
0x14000421c  mov     r8, r13; lpMem
0x14000421f  xor     edx, edx; dwFlags
0x140004221  mov     esi, eax
0x140004223  call    cs:__imp_HeapFree
0x14000422a  nop     dword ptr [rax+rax+00h]
0x14000422f  jmp     loc_140004161
0x140004234  mov     ecx, esi; dwErrCode
0x140004236  call    cs:__imp_SetLastError
0x14000423d  nop     dword ptr [rax+rax+00h]
0x140004242  xor     eax, eax
0x140004244  add     rsp, 80h
0x14000424b  pop     rsi
0x14000424c  retn
0x14000424e  mov     ecx, ebx; dwErrCode
0x140004250  call    cs:__imp_SetLastError
0x140004257  nop     dword ptr [rax+rax+00h]
0x14000425c  cmp     ebx, 5
0x14000425f  jz      short loc_140004277
0x140004261  mov     r8d, ebx
0x140004264  lea     rdx, aRegopencurrent; "RegOpenCurrentUser failed. Error %d."
0x14000426b  lea     rcx, aSplgetclientus; "SplGetClientUserHandle"
0x140004272  call    ?WriteDbgTraceError@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x140004277  mov     rcx, [rsp+88h+hKey]; hKey
0x14000427f  test    rcx, rcx
0x140004282  jz      short loc_140004290
0x140004284  call    cs:__imp_RegCloseKey
0x14000428b  nop     dword ptr [rax+rax+00h]
0x140004290  mov     r14, r12
0x140004293  mov     [rsp+88h+hKey], r12
0x14000429b  jmp     loc_1400040E0
0x1400042a0  call    cs:__imp_GetLastError
0x1400042a7  nop     dword ptr [rax+rax+00h]
0x1400042ac  cmp     eax, 5
0x1400042af  jnz     loc_1400040E9
0x1400042b5  mov     ecx, 20019h
0x1400042ba  call    SplGetClientUserHandle
0x1400042bf  mov     r14, rax
0x1400042c2  jmp     loc_1400040E9
0x1400042c7  mov     r8, rbp; unsigned __int16 *
0x1400042ca  mov     edx, 21Ch; unsigned __int64
0x1400042cf  mov     rcx, r10; unsigned __int16 *
0x1400042d2  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1400042d7  jmp     loc_1400041D2
```
