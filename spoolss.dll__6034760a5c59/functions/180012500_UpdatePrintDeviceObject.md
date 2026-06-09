# UpdatePrintDeviceObject

- ea: `0x180012500`
- end: `0x180012641`
- name: `UpdatePrintDeviceObject`
- size: `321`
- prototype: `__int64 __fastcall(HANDLE hPrinter, struct _DEVICEOBJECT *)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, installer_update`

## callees

- `0x180001b50`
- `0x1800048b4`
- `0x1800111f0`
- `0x180011b94`
- `0x180011d48`
- `0x180012288`
- `0x180012500`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180012575`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800125e6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180012575`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800125e6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180012585`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001260e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180012585`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001260e`

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
0x180012500  mov     rax, rsp
0x180012503  mov     [rax+18h], rbx
0x180012507  mov     [rax+20h], rbp
0x18001250b  push    rsi
0x18001250c  push    rdi
0x18001250d  push    r14
0x18001250f  sub     rsp, 20h
0x180012513  mov     qword ptr [rax+8], 0
0x18001251b  mov     rdi, rdx
0x18001251e  mov     qword ptr [rax+10h], 0
0x180012526  mov     rbp, rcx
0x180012529  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18001252d  jz      loc_180012629
0x180012533  cmp     rdx, 0FFFFFFFFFFFFFFFFh
0x180012537  jz      loc_180012629
0x18001253d  xor     edx, edx
0x18001253f  mov     rcx, rdi
0x180012542  call    ?eProtectHandle@@YA?AW4EProtectResult@@PEAXH@Z; eProtectHandle(void *,int)
0x180012547  cmp     eax, 1
0x18001254a  jnz     short loc_180012556
0x18001254c  mov     eax, 80070006h
0x180012551  jmp     loc_18001262E
0x180012556  lea     r14, [rdi+20h]
0x18001255a  mov     rcx, rbp; hPrinter
0x18001255d  mov     rdx, [r14]; this
0x180012560  call    ?UpdateDevnode@@YAJPEAX0@Z; UpdateDevnode(void *,void *)
0x180012565  mov     esi, eax
0x180012567  cmp     eax, 8007139Fh
0x18001256c  jnz     short loc_1800125DD
0x18001256e  lea     rcx, ?DevObjSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180012575  call    cs:__imp_EnterCriticalSection
0x18001257b  mov     ebx, [rdi+18h]
0x18001257e  lea     rcx, ?DevObjSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180012585  call    cs:__imp_LeaveCriticalSection
0x18001258b  cmp     ebx, 1
0x18001258e  jnz     short loc_1800125DD
0x180012590  mov     rcx, [r14]; this
0x180012593  call    ?DeleteDevnode@@YAJPEAX@Z; DeleteDevnode(void *)
0x180012598  lea     r9, [rsp+38h+arg_8]; unsigned __int16 **
0x18001259d  mov     rdx, r14; void **
0x1800125a0  lea     r8, [rsp+38h+arg_0]; unsigned __int16 **
0x1800125a5  mov     rcx, rbp; hPrinter
0x1800125a8  call    ?AddDevnode@@YAJPEAXPEAPEAXPEAPEAG2@Z; AddDevnode(void *,void * *,ushort * *,ushort * *)
0x1800125ad  mov     rcx, [rdi+28h]
0x1800125b1  mov     esi, eax
0x1800125b3  test    rcx, rcx
0x1800125b6  jz      short loc_1800125BD
0x1800125b8  call    DllFreeSplMem
0x1800125bd  mov     rcx, [rdi+30h]
0x1800125c1  test    rcx, rcx
0x1800125c4  jz      short loc_1800125CB
0x1800125c6  call    DllFreeSplMem
0x1800125cb  mov     rax, [rsp+38h+arg_0]
0x1800125d0  mov     [rdi+28h], rax
0x1800125d4  mov     rax, [rsp+38h+arg_8]
0x1800125d9  mov     [rdi+30h], rax
0x1800125dd  lea     rcx, ?DevObjSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800125e4  xor     ebx, ebx
0x1800125e6  call    cs:__imp_EnterCriticalSection
0x1800125ec  add     dword ptr [rdi+1Ch], 0FFFFFFFFh
0x1800125f0  jnz     short loc_180012607
0x1800125f2  mov     eax, [rdi+18h]
0x1800125f5  test    al, 4
0x1800125f7  jz      short loc_180012607
0x1800125f9  and     eax, 0FFFFFFFBh
0x1800125fc  mov     ebx, 1
0x180012601  or      eax, 2
0x180012604  mov     [rdi+18h], eax
0x180012607  lea     rcx, ?DevObjSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18001260e  call    cs:__imp_LeaveCriticalSection
0x180012614  test    ebx, ebx
0x180012616  jz      short loc_180012625
0x180012618  mov     rcx, rdi; struct _DEVICEOBJECT *
0x18001261b  call    ?FreeDevObjHandle@@YAXPEAU_DEVICEOBJECT@@@Z; FreeDevObjHandle(_DEVICEOBJECT *)
0x180012620  mov     esi, 80070771h
0x180012625  mov     eax, esi
0x180012627  jmp     short loc_18001262E
0x180012629  mov     eax, 80070057h
0x18001262e  mov     rbx, [rsp+38h+arg_10]
0x180012633  mov     rbp, [rsp+38h+arg_18]
0x180012638  add     rsp, 20h
0x18001263c  pop     r14
0x18001263e  pop     rdi
0x18001263f  pop     rsi
0x180012640  retn
```
