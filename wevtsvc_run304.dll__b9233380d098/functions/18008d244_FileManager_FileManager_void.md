# FileManager::FileManager(void)

- ea: `0x18008d244`
- end: `0x18008d301`
- name: `??0FileManager@@QEAA@XZ`
- size: `189`
- prototype: `FileManager *__fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800978a0`

## callees

- `0x18000bf10`
- `0x18008d244`
- `0x180092008`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18008d2f2`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18008d2f2`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18008d280`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18008d280`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008d2b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008d2b1`

## pseudocode

```c
FileManager *__fastcall FileManager::FileManager(PVOID pv)
{
  _QWORD *v2; // rcx
  struct _TP_TIMER *ThreadpoolTimer; // rax
  DWORD LastError; // eax
  struct _FILETIME pftDueTime; // [rsp+30h] [rbp+8h] BYREF

  utl::vector<BinXmlReader::TmplInstInfo,utl::allocator<BinXmlReader::TmplInstInfo>>::vector<BinXmlReader::TmplInstInfo,utl::allocator<BinXmlReader::TmplInstInfo>>(pv);
  v2[3] = 0;
  v2[4] = 0;
  v2[5] = 0;
  utl::vector<BinXmlReader::TmplInstInfo,utl::allocator<BinXmlReader::TmplInstInfo>>::vector<BinXmlReader::TmplInstInfo,utl::allocator<BinXmlReader::TmplInstInfo>>(v2 + 6);
  ThreadpoolTimer = CreateThreadpoolTimer(FileManager::FreeEventBufferCallback, pv, 0);
  *((_QWORD *)pv + 5) = ThreadpoolTimer;
  if ( ThreadpoolTimer )
  {
    pftDueTime = (struct _FILETIME)-1500000000LL;
    SetThreadpoolTimer(ThreadpoolTimer, &pftDueTime, 0, 0xBB8u);
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
         && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
  {
    LastError = GetLastError();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_d33d9432658b3ff029c702686d00d94e_Traceguids, LastError);
  }
  return (FileManager *)pv;
}

```

## disassembly

```asm
0x18008d244  push    rbx
0x18008d246  sub     rsp, 20h
0x18008d24a  mov     rbx, rcx
0x18008d24d  call    ??0?$vector@UTmplInstInfo@BinXmlReader@@V?$allocator@UTmplInstInfo@BinXmlReader@@@utl@@@utl@@QEAA@XZ; utl::vector<BinXmlReader::TmplInstInfo,utl::allocator<BinXmlReader::TmplInstInfo>>::vector<BinXmlReader::TmplInstInfo,utl::allocator<BinXmlReader::TmplInstInfo>>(void)
0x18008d252  mov     qword ptr [rcx+18h], 0
0x18008d25a  mov     qword ptr [rcx+20h], 0
0x18008d262  mov     qword ptr [rcx+28h], 0
0x18008d26a  add     rcx, 30h ; '0'; void *
0x18008d26e  call    ??0?$vector@UTmplInstInfo@BinXmlReader@@V?$allocator@UTmplInstInfo@BinXmlReader@@@utl@@@utl@@QEAA@XZ; utl::vector<BinXmlReader::TmplInstInfo,utl::allocator<BinXmlReader::TmplInstInfo>>::vector<BinXmlReader::TmplInstInfo,utl::allocator<BinXmlReader::TmplInstInfo>>(void)
0x18008d273  xor     r8d, r8d; pcbe
0x18008d276  lea     rcx, ?FreeEventBufferCallback@FileManager@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18008d27d  mov     rdx, rbx; pv
0x18008d280  call    cs:__imp_CreateThreadpoolTimer
0x18008d286  mov     [rbx+28h], rax
0x18008d28a  test    rax, rax
0x18008d28d  jnz     short loc_18008D2D8
0x18008d28f  mov     rax, cs:WPP_GLOBAL_Control
0x18008d296  lea     rcx, WPP_GLOBAL_Control
0x18008d29d  cmp     rax, rcx
0x18008d2a0  jz      short loc_18008D2F8
0x18008d2a2  test    dword ptr [rax+1Ch], 8000h
0x18008d2a9  jz      short loc_18008D2F8
0x18008d2ab  cmp     byte ptr [rax+19h], 3
0x18008d2af  jb      short loc_18008D2F8
0x18008d2b1  call    cs:__imp_GetLastError
0x18008d2b7  mov     rcx, cs:WPP_GLOBAL_Control
0x18008d2be  lea     r8, WPP_d33d9432658b3ff029c702686d00d94e_Traceguids
0x18008d2c5  mov     edx, 0Ah
0x18008d2ca  mov     r9d, eax
0x18008d2cd  mov     rcx, [rcx+10h]
0x18008d2d1  call    WPP_SF_d
0x18008d2d6  jmp     short loc_18008D2F8
0x18008d2d8  mov     r9d, 0BB8h; msWindowLength
0x18008d2de  mov     qword ptr [rsp+28h+pftDueTime.dwLowDateTime], 0FFFFFFFFA697D100h
0x18008d2e7  xor     r8d, r8d; msPeriod
0x18008d2ea  lea     rdx, [rsp+28h+pftDueTime]; pftDueTime
0x18008d2ef  mov     rcx, rax; pti
0x18008d2f2  call    cs:__imp_SetThreadpoolTimer
0x18008d2f8  mov     rax, rbx
0x18008d2fb  add     rsp, 20h
0x18008d2ff  pop     rbx
0x18008d300  retn
```
