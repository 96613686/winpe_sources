# WinStationBSMWorkerThread(void *)

- ea: `0x180012a50`
- end: `0x180012b0e`
- name: `?WinStationBSMWorkerThread@@YAKPEAX@Z`
- size: `190`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180007890`
- `0x180012a50`
- `0x180012b14`
- `0x1800295f4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180012af1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180012af1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180012ac7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180012ac7`

## string_xrefs

- `0x180012ad2`: `WinStationBSMWorkerThread(): caller failed to wait for me!`

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
0x180012a50  mov     r11, rsp
0x180012a53  push    rbx
0x180012a54  push    rbp
0x180012a55  push    rsi
0x180012a56  push    rdi
0x180012a57  sub     rsp, 78h
0x180012a5b  mov     r9d, [rcx+10h]; unsigned int
0x180012a5f  lea     rdx, [rcx+30h]
0x180012a63  lea     r8, [rcx+18h]
0x180012a67  mov     rbx, rcx
0x180012a6a  xor     edi, edi
0x180012a6c  cmp     [rcx+54h], edi
0x180012a6f  setnz   al
0x180012a72  mov     [rsp+98h+var_30], al; unsigned __int8
0x180012a76  mov     eax, [rcx+50h]
0x180012a79  mov     [rsp+98h+var_38], eax; unsigned int
0x180012a7d  mov     rax, [rcx+48h]
0x180012a81  mov     [r11-40h], rax
0x180012a85  mov     eax, [rcx+34h]
0x180012a88  mov     [rsp+98h+var_48], eax; unsigned int
0x180012a8c  mov     rax, [rcx+28h]
0x180012a90  mov     [r11-50h], rdx
0x180012a94  mov     edx, [rcx+8]; int
0x180012a97  mov     [r11-58h], rax
0x180012a9b  mov     rax, [rcx+20h]
0x180012a9f  mov     [r11-60h], rax
0x180012aa3  mov     eax, [rcx+1Ch]
0x180012aa6  mov     [rsp+98h+var_68], eax; unsigned int
0x180012aaa  mov     eax, [rcx+14h]
0x180012aad  mov     [r11-70h], r8
0x180012ab1  mov     r8d, [rcx+0Ch]; unsigned int
0x180012ab5  mov     rcx, [rcx]; this
0x180012ab8  mov     [rsp+98h+var_78], eax; unsigned int
0x180012abc  call    ?WinStationBroadcastSystemMessageWorker@@YAJPEAXHKKKPEAKK_K_JPEAJKPEAEKE@Z; WinStationBroadcastSystemMessageWorker(void *,int,ulong,ulong,ulong,ulong *,ulong,unsigned __int64,__int64,long *,ulong,uchar *,ulong,uchar)
0x180012ac1  lea     rcx, [rbx+58h]; lpCriticalSection
0x180012ac5  mov     esi, eax
0x180012ac7  call    cs:__imp_EnterCriticalSection
0x180012acd  cmp     [rbx+3Ch], edi
0x180012ad0  jz      short loc_180012AE6
0x180012ad2  lea     rdx, aWinstationbsmw; "WinStationBSMWorkerThread(): caller fai"...
0x180012ad9  lea     ecx, [rdi+8]; int
0x180012adc  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180012ae1  mov     edi, 1
0x180012ae6  lea     rcx, [rbx+58h]; lpCriticalSection
0x180012aea  mov     dword ptr [rbx+38h], 1
0x180012af1  call    cs:__imp_LeaveCriticalSection
0x180012af7  test    edi, edi
0x180012af9  jz      short loc_180012B03
0x180012afb  mov     rcx, rbx; this
0x180012afe  call    ??_GBSM_DATA_PACKAGE@@QEAAPEAXI@Z; BSM_DATA_PACKAGE::`scalar deleting destructor'(uint)
0x180012b03  mov     eax, esi
0x180012b05  add     rsp, 78h
0x180012b09  pop     rdi
0x180012b0a  pop     rsi
0x180012b0b  pop     rbp
0x180012b0c  pop     rbx
0x180012b0d  retn
```
