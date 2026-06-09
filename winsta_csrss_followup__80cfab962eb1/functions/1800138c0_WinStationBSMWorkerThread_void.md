# WinStationBSMWorkerThread(void *)

- ea: `0x1800138c0`
- end: `0x18001398b`
- name: `?WinStationBSMWorkerThread@@YAKPEAX@Z`
- size: `203`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180005b40`
- `0x1800138c0`
- `0x180013994`
- `0x18002b228`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180013967`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180013967`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180013937`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180013937`

## string_xrefs

- `0x180013948`: `WinStationBSMWorkerThread(): caller failed to wait for me!`

## pseudocode

```c
__int64 __fastcall WinStationBSMWorkerThread(char *Parameter)
{
  int v2; // edi
  unsigned int v3; // esi
  unsigned int v4; // edx

  v2 = 0;
  v3 = WinStationBroadcastSystemMessageWorker(
         *(CPublicBinding **)Parameter,
         *((_DWORD *)Parameter + 2),
         *((_DWORD *)Parameter + 3),
         *((_DWORD *)Parameter + 4),
         *((_DWORD *)Parameter + 5),
         (unsigned int *)Parameter + 6,
         *((_DWORD *)Parameter + 7),
         *((_QWORD *)Parameter + 4),
         *((_QWORD *)Parameter + 5),
         (int *)Parameter + 12,
         *((_DWORD *)Parameter + 13),
         *((unsigned __int8 **)Parameter + 9),
         *((_DWORD *)Parameter + 20),
         *((_DWORD *)Parameter + 21) != 0);
  EnterCriticalSection((LPCRITICAL_SECTION)(Parameter + 88));
  if ( *((_DWORD *)Parameter + 15) )
  {
    _DbgPrintMessage(8, "WinStationBSMWorkerThread(): caller failed to wait for me!");
    v2 = 1;
  }
  *((_DWORD *)Parameter + 14) = 1;
  LeaveCriticalSection((LPCRITICAL_SECTION)(Parameter + 88));
  if ( v2 )
    BSM_DATA_PACKAGE::`scalar deleting destructor'((BSM_DATA_PACKAGE *)Parameter, v4);
  return v3;
}

```

## disassembly

```asm
0x1800138c0  mov     r11, rsp
0x1800138c3  push    rbx
0x1800138c4  push    rbp
0x1800138c5  push    rsi
0x1800138c6  push    rdi
0x1800138c7  sub     rsp, 78h
0x1800138cb  mov     r9d, [rcx+10h]; unsigned int
0x1800138cf  lea     rdx, [rcx+30h]
0x1800138d3  lea     r8, [rcx+18h]
0x1800138d7  mov     rbx, rcx
0x1800138da  xor     edi, edi
0x1800138dc  cmp     [rcx+54h], edi
0x1800138df  setnz   al
0x1800138e2  mov     [rsp+98h+var_30], al; unsigned __int8
0x1800138e6  mov     eax, [rcx+50h]
0x1800138e9  mov     [rsp+98h+var_38], eax; unsigned int
0x1800138ed  mov     rax, [rcx+48h]
0x1800138f1  mov     [r11-40h], rax
0x1800138f5  mov     eax, [rcx+34h]
0x1800138f8  mov     [rsp+98h+var_48], eax; unsigned int
0x1800138fc  mov     rax, [rcx+28h]
0x180013900  mov     [r11-50h], rdx
0x180013904  mov     edx, [rcx+8]; int
0x180013907  mov     [r11-58h], rax
0x18001390b  mov     rax, [rcx+20h]
0x18001390f  mov     [r11-60h], rax
0x180013913  mov     eax, [rcx+1Ch]
0x180013916  mov     [rsp+98h+var_68], eax; unsigned int
0x18001391a  mov     eax, [rcx+14h]
0x18001391d  mov     [r11-70h], r8
0x180013921  mov     r8d, [rcx+0Ch]; unsigned int
0x180013925  mov     rcx, [rcx]; this
0x180013928  mov     [rsp+98h+var_78], eax; unsigned int
0x18001392c  call    ?WinStationBroadcastSystemMessageWorker@@YAJPEAXHKKKPEAKK_K_JPEAJKPEAEKE@Z; WinStationBroadcastSystemMessageWorker(void *,int,ulong,ulong,ulong,ulong *,ulong,unsigned __int64,__int64,long *,ulong,uchar *,ulong,uchar)
0x180013931  lea     rcx, [rbx+58h]; lpCriticalSection
0x180013935  mov     esi, eax
0x180013937  call    cs:__imp_EnterCriticalSection
0x18001393e  nop     dword ptr [rax+rax+00h]
0x180013943  cmp     [rbx+3Ch], edi
0x180013946  jz      short loc_18001395C
0x180013948  lea     rdx, aWinstationbsmw; "WinStationBSMWorkerThread(): caller fai"...
0x18001394f  lea     ecx, [rdi+8]; int
0x180013952  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180013957  mov     edi, 1
0x18001395c  lea     rcx, [rbx+58h]; lpCriticalSection
0x180013960  mov     dword ptr [rbx+38h], 1
0x180013967  call    cs:__imp_LeaveCriticalSection
0x18001396e  nop     dword ptr [rax+rax+00h]
0x180013973  test    edi, edi
0x180013975  jz      short loc_18001397F
0x180013977  mov     rcx, rbx; this
0x18001397a  call    ??_GBSM_DATA_PACKAGE@@QEAAPEAXI@Z; BSM_DATA_PACKAGE::`scalar deleting destructor'(uint)
0x18001397f  mov     eax, esi
0x180013981  add     rsp, 78h
0x180013985  pop     rdi
0x180013986  pop     rsi
0x180013987  pop     rbp
0x180013988  pop     rbx
0x180013989  retn
```
