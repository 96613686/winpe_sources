# UpdatePrintDeviceObject

- ea: `0x180013c20`
- end: `0x180013d7a`
- name: `UpdatePrintDeviceObject`
- size: `346`
- prototype: `__int64 __fastcall(HANDLE hPrinter, struct _DEVICEOBJECT *)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, installer_update`

## callees

- `0x180001b60`
- `0x180004bf4`
- `0x18001285c`
- `0x18001329c`
- `0x18001346c`
- `0x180013a04`
- `0x180013c20`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180013c95`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180013d12`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180013c95`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180013d12`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180013cab`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180013d40`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180013cab`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180013d40`

## pseudocode

```c
__int64 __fastcall UpdatePrintDeviceObject(HANDLE hPrinter, DeviceObject **a2)
{
  unsigned int updated; // esi
  int v6; // ebx
  unsigned int v7; // eax
  DeviceObject *v8; // rcx
  DeviceObject *v9; // rcx
  int v10; // ebx
  int v12; // eax
  unsigned __int16 *v13; // [rsp+40h] [rbp+8h] BYREF
  unsigned __int16 *v14; // [rsp+48h] [rbp+10h] BYREF

  v13 = 0;
  v14 = 0;
  if ( hPrinter == (HANDLE)-1LL || a2 == (DeviceObject **)-1LL )
    return 2147942487LL;
  if ( (unsigned int)eProtectHandle(a2, 0) == 1 )
    return 2147942406LL;
  updated = UpdateDevnode(hPrinter, a2[4]);
  if ( updated == -2147019873 )
  {
    EnterCriticalSection(&DevObjSection);
    v6 = *((_DWORD *)a2 + 6);
    LeaveCriticalSection(&DevObjSection);
    if ( v6 == 1 )
    {
      DeleteDevnode(a2[4]);
      v7 = AddDevnode(hPrinter, (void **)a2 + 4, &v13, &v14);
      v8 = a2[5];
      updated = v7;
      if ( v8 )
        DllFreeSplMem(v8);
      v9 = a2[6];
      if ( v9 )
        DllFreeSplMem(v9);
      a2[5] = (DeviceObject *)v13;
      a2[6] = (DeviceObject *)v14;
    }
  }
  v10 = 0;
  EnterCriticalSection(&DevObjSection);
  if ( (*((_DWORD *)a2 + 7))-- == 1 )
  {
    v12 = *((_DWORD *)a2 + 6);
    if ( (v12 & 4) != 0 )
    {
      v10 = 1;
      *((_DWORD *)a2 + 6) = v12 & 0xFFFFFFF9 | 2;
    }
  }
  LeaveCriticalSection(&DevObjSection);
  if ( v10 )
  {
    FreeDevObjHandle((struct _DEVICEOBJECT *)a2);
    return (unsigned int)-2147022991;
  }
  return updated;
}

```

## disassembly

```asm
0x180013c20  mov     rax, rsp
0x180013c23  mov     [rax+18h], rbx
0x180013c27  mov     [rax+20h], rbp
0x180013c2b  push    rsi
0x180013c2c  push    rdi
0x180013c2d  push    r14
0x180013c2f  sub     rsp, 20h
0x180013c33  mov     qword ptr [rax+8], 0
0x180013c3b  mov     rdi, rdx
0x180013c3e  mov     qword ptr [rax+10h], 0
0x180013c46  mov     rbp, rcx
0x180013c49  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180013c4d  jz      loc_180013D61
0x180013c53  cmp     rdx, 0FFFFFFFFFFFFFFFFh
0x180013c57  jz      loc_180013D61
0x180013c5d  xor     edx, edx
0x180013c5f  mov     rcx, rdi
0x180013c62  call    ?eProtectHandle@@YA?AW4EProtectResult@@PEAXH@Z; eProtectHandle(void *,int)
0x180013c67  cmp     eax, 1
0x180013c6a  jnz     short loc_180013C76
0x180013c6c  mov     eax, 80070006h
0x180013c71  jmp     loc_180013D66
0x180013c76  lea     r14, [rdi+20h]
0x180013c7a  mov     rcx, rbp; hPrinter
0x180013c7d  mov     rdx, [r14]; this
0x180013c80  call    ?UpdateDevnode@@YAJPEAX0@Z; UpdateDevnode(void *,void *)
0x180013c85  mov     esi, eax
0x180013c87  cmp     eax, 8007139Fh
0x180013c8c  jnz     short loc_180013D09
0x180013c8e  lea     rcx, ?DevObjSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180013c95  call    cs:__imp_EnterCriticalSection
0x180013c9c  nop     dword ptr [rax+rax+00h]
0x180013ca1  mov     ebx, [rdi+18h]
0x180013ca4  lea     rcx, ?DevObjSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180013cab  call    cs:__imp_LeaveCriticalSection
0x180013cb2  nop     dword ptr [rax+rax+00h]
0x180013cb7  cmp     ebx, 1
0x180013cba  jnz     short loc_180013D09
0x180013cbc  mov     rcx, [r14]; this
0x180013cbf  call    ?DeleteDevnode@@YAJPEAX@Z; DeleteDevnode(void *)
0x180013cc4  lea     r9, [rsp+38h+arg_8]; unsigned __int16 **
0x180013cc9  mov     rdx, r14; void **
0x180013ccc  lea     r8, [rsp+38h+arg_0]; unsigned __int16 **
0x180013cd1  mov     rcx, rbp; hPrinter
0x180013cd4  call    ?AddDevnode@@YAJPEAXPEAPEAXPEAPEAG2@Z; AddDevnode(void *,void * *,ushort * *,ushort * *)
0x180013cd9  mov     rcx, [rdi+28h]
0x180013cdd  mov     esi, eax
0x180013cdf  test    rcx, rcx
0x180013ce2  jz      short loc_180013CE9
0x180013ce4  call    DllFreeSplMem
0x180013ce9  mov     rcx, [rdi+30h]
0x180013ced  test    rcx, rcx
0x180013cf0  jz      short loc_180013CF7
0x180013cf2  call    DllFreeSplMem
0x180013cf7  mov     rax, [rsp+38h+arg_0]
0x180013cfc  mov     [rdi+28h], rax
0x180013d00  mov     rax, [rsp+38h+arg_8]
0x180013d05  mov     [rdi+30h], rax
0x180013d09  lea     rcx, ?DevObjSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180013d10  xor     ebx, ebx
0x180013d12  call    cs:__imp_EnterCriticalSection
0x180013d19  nop     dword ptr [rax+rax+00h]
0x180013d1e  add     dword ptr [rdi+1Ch], 0FFFFFFFFh
0x180013d22  jnz     short loc_180013D39
0x180013d24  mov     eax, [rdi+18h]
0x180013d27  test    al, 4
0x180013d29  jz      short loc_180013D39
0x180013d2b  and     eax, 0FFFFFFFBh
0x180013d2e  mov     ebx, 1
0x180013d33  or      eax, 2
0x180013d36  mov     [rdi+18h], eax
0x180013d39  lea     rcx, ?DevObjSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180013d40  call    cs:__imp_LeaveCriticalSection
0x180013d47  nop     dword ptr [rax+rax+00h]
0x180013d4c  test    ebx, ebx
0x180013d4e  jz      short loc_180013D5D
0x180013d50  mov     rcx, rdi; struct _DEVICEOBJECT *
0x180013d53  call    ?FreeDevObjHandle@@YAXPEAU_DEVICEOBJECT@@@Z; FreeDevObjHandle(_DEVICEOBJECT *)
0x180013d58  mov     esi, 80070771h
0x180013d5d  mov     eax, esi
0x180013d5f  jmp     short loc_180013D66
0x180013d61  mov     eax, 80070057h
0x180013d66  mov     rbx, [rsp+38h+arg_10]
0x180013d6b  mov     rbp, [rsp+38h+arg_18]
0x180013d70  add     rsp, 20h
0x180013d74  pop     r14
0x180013d76  pop     rdi
0x180013d77  pop     rsi
0x180013d78  retn
```
