# File::PossiblyScheduleTimer(void)

- ea: `0x180032b4c`
- end: `0x180032bca`
- name: `?PossiblyScheduleTimer@File@@AEAAXXZ`
- size: `126`
- prototype: `void __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18003316c`

## callees

- `0x180032b4c`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180032b6e`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180032b6e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180032bb7`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180032bb7`

## pseudocode

```c
void __fastcall File::PossiblyScheduleTimer(_QWORD *pv)
{
  struct _TP_TIMER *v2; // rcx
  PTP_TIMER ThreadpoolTimer; // rax
  struct _FILETIME pftDueTime; // [rsp+30h] [rbp+8h] BYREF

  v2 = (struct _TP_TIMER *)pv[82];
  if ( v2
    || (ThreadpoolTimer = CreateThreadpoolTimer(File::FlushTimerCallback, pv, 0),
        pv[82] = ThreadpoolTimer,
        (v2 = ThreadpoolTimer) != 0) )
  {
    if ( !*((_BYTE *)pv + 837) )
    {
      pftDueTime = (struct _FILETIME)((-(__int64)(*((_BYTE *)pv + 831) != 0) & 0xFFFFFFFFEE1E5D00uLL) - 300000000);
      SetThreadpoolTimer(v2, &pftDueTime, 0, 0x1Eu);
      *((_BYTE *)pv + 837) = 1;
    }
  }
}

```

## disassembly

```asm
0x180032b4c  push    rbx
0x180032b4e  sub     rsp, 20h
0x180032b52  mov     rbx, rcx
0x180032b55  mov     rcx, [rcx+290h]
0x180032b5c  test    rcx, rcx
0x180032b5f  jnz     short loc_180032B83
0x180032b61  xor     r8d, r8d; pcbe
0x180032b64  lea     rcx, ?FlushTimerCallback@File@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180032b6b  mov     rdx, rbx; pv
0x180032b6e  call    cs:__imp_CreateThreadpoolTimer
0x180032b74  mov     [rbx+290h], rax
0x180032b7b  mov     rcx, rax; pti
0x180032b7e  test    rax, rax
0x180032b81  jz      short loc_180032BC4
0x180032b83  cmp     byte ptr [rbx+345h], 0
0x180032b8a  jnz     short loc_180032BC4
0x180032b8c  mov     al, [rbx+33Fh]
0x180032b92  mov     r9d, 1Eh; msWindowLength
0x180032b98  neg     al
0x180032b9a  mov     rax, 0FFFFFFFFEE1E5D00h
0x180032ba1  sbb     rdx, rdx
0x180032ba4  xor     r8d, r8d; msPeriod
0x180032ba7  and     rdx, rax
0x180032baa  add     rdx, rax
0x180032bad  mov     qword ptr [rsp+28h+pftDueTime.dwLowDateTime], rdx
0x180032bb2  lea     rdx, [rsp+28h+pftDueTime]; pftDueTime
0x180032bb7  call    cs:__imp_SetThreadpoolTimer
0x180032bbd  mov     byte ptr [rbx+345h], 1
0x180032bc4  add     rsp, 20h
0x180032bc8  pop     rbx
0x180032bc9  retn
```
