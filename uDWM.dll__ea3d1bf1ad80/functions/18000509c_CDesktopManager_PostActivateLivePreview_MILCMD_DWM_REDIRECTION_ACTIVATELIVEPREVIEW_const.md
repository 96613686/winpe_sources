# CDesktopManager::PostActivateLivePreview(MILCMD_DWM_REDIRECTION_ACTIVATELIVEPREVIEW const *)

- ea: `0x18000509c`
- end: `0x1800051f8`
- name: `?PostActivateLivePreview@CDesktopManager@@QEAAJPEBUMILCMD_DWM_REDIRECTION_ACTIVATELIVEPREVIEW@@@Z`
- size: `348`
- prototype: `__int64 __fastcall(CDesktopManager *__hidden this, const struct MILCMD_DWM_REDIRECTION_ACTIVATELIVEPREVIEW *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x1800059ac`
- `0x1800dd4c4`

## callees

- `0x18000509c`
- `0x18001f43c`
- `0x1800827d0`
- `0x180083f40`
- `0x180095b34`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800051ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800051ac`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000518b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000518b`
- `USER32!PostThreadMessageW` at `0x1800051a2`
- `USER32!PostThreadMessageW` at `0x1800051a2`

## pseudocode

```c
__int64 __fastcall CDesktopManager::PostActivateLivePreview(
        CDesktopManager *this,
        const struct MILCMD_DWM_REDIRECTION_ACTIVATELIVEPREVIEW *a2)
{
  char *v4; // rdi
  signed int v5; // ebx
  __int16 v6; // ax
  __int16 v7; // ax
  char *v8; // rax
  char *v9; // rbp
  signed int LastError; // eax
  unsigned int v12; // [rsp+20h] [rbp-38h]

  if ( !*((_DWORD *)this + 282) )
  {
    v4 = 0;
    v5 = -2147467259;
    v12 = 2670;
LABEL_3:
    MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v5, v12, 0);
    goto LABEL_19;
  }
  v6 = *((_WORD *)a2 + 4);
  if ( *((_DWORD *)a2 + 7) )
    v7 = 8 * (v6 + 4) + 16 * v6;
  else
    v7 = 8 * (v6 + 4);
  v8 = (char *)DefaultHeap::Alloc(v7);
  v4 = v8;
  if ( v8 )
  {
    v9 = v8 + 32;
    *(_DWORD *)v8 = *((_DWORD *)a2 + 1);
    *((_DWORD *)v8 + 1) = *((_DWORD *)a2 + 2);
    *((_QWORD *)v8 + 1) = *(_QWORD *)((char *)a2 + 12);
    *((_DWORD *)v8 + 4) = *((_DWORD *)a2 + 5);
    *((_DWORD *)v8 + 5) = *((_DWORD *)a2 + 6);
    *((_DWORD *)v8 + 6) = 0;
    *((_DWORD *)v8 + 7) = *((_DWORD *)a2 + 7);
    memcpy_0(v8 + 32, (char *)a2 + 32, (unsigned int)(8 * *((_DWORD *)a2 + 2)));
    if ( *((_DWORD *)a2 + 7) )
      memcpy_0(
        &v9[8 * *((unsigned int *)a2 + 2)],
        (char *)a2 + 8 * *((unsigned int *)a2 + 2) + 32,
        (unsigned int)(16 * *((_DWORD *)a2 + 2)));
    SetLastError(0);
    if ( !PostThreadMessageW(*((_DWORD *)this + 282), 0x405u, (WPARAM)v4, 0) )
    {
      LastError = GetLastError();
      v5 = LastError;
      if ( LastError > 0 )
        v5 = (unsigned __int16)LastError | 0x80070000;
      v12 = 2708;
      if ( v5 >= 0 )
        v5 = -2003304445;
      goto LABEL_3;
    }
    v4 = 0;
    v5 = 0;
  }
  else
  {
    v5 = -2147024882;
    MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, -2147024882, 0xA79u, 0);
  }
LABEL_19:
  DefaultHeap::Free(v4);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18000509c  push    rbx
0x18000509e  push    rbp
0x18000509f  push    rsi
0x1800050a0  push    rdi
0x1800050a1  sub     rsp, 38h
0x1800050a5  cmp     dword ptr [rcx+468h], 0
0x1800050ac  mov     rbx, rdx
0x1800050af  mov     rsi, rcx
0x1800050b2  jnz     short loc_1800050DD
0x1800050b4  xor     edi, edi
0x1800050b6  mov     ebx, 80004005h
0x1800050bb  mov     [rsp+58h+var_30], rdi; void *
0x1800050c0  mov     [rsp+58h+var_38], 0A6Eh; unsigned int
0x1800050c8  xor     edx, edx; int *
0x1800050ca  mov     r9d, ebx; int
0x1800050cd  xor     r8d, r8d; unsigned int
0x1800050d0  lea     ecx, [rdx+14h]; unsigned int
0x1800050d3  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x1800050d8  jmp     loc_1800051E5
0x1800050dd  movzx   eax, word ptr [rdx+8]
0x1800050e1  lea     ecx, [rax+4]
0x1800050e4  shl     cx, 3
0x1800050e8  cmp     dword ptr [rdx+1Ch], 0
0x1800050ec  jz      short loc_1800050F7
0x1800050ee  shl     ax, 4
0x1800050f2  add     ax, cx
0x1800050f5  jmp     short loc_1800050FA
0x1800050f7  movzx   eax, cx
0x1800050fa  movsx   rcx, ax; unsigned __int64
0x1800050fe  call    ?Alloc@DefaultHeap@@SAPEAX_K@Z; DefaultHeap::Alloc(unsigned __int64)
0x180005103  mov     rdi, rax
0x180005106  test    rax, rax
0x180005109  jnz     short loc_18000511F
0x18000510b  mov     [rsp+58h+var_30], rax
0x180005110  mov     ebx, 8007000Eh
0x180005115  mov     [rsp+58h+var_38], 0A79h
0x18000511d  jmp     short loc_1800050C8
0x18000511f  mov     eax, [rbx+4]
0x180005122  lea     rbp, [rdi+20h]
0x180005126  mov     [rdi], eax
0x180005128  lea     rdx, [rbx+20h]; Src
0x18000512c  mov     eax, [rbx+8]
0x18000512f  mov     rcx, rbp; void *
0x180005132  mov     [rdi+4], eax
0x180005135  mov     rax, [rbx+0Ch]
0x180005139  mov     [rdi+8], rax
0x18000513d  mov     eax, [rbx+14h]
0x180005140  mov     [rdi+10h], eax
0x180005143  mov     eax, [rbx+18h]
0x180005146  mov     [rdi+14h], eax
0x180005149  mov     dword ptr [rdi+18h], 0
0x180005150  mov     eax, [rbx+1Ch]
0x180005153  mov     [rdi+1Ch], eax
0x180005156  mov     r8d, [rbx+8]
0x18000515a  shl     r8d, 3; Size
0x18000515e  call    memcpy_0
0x180005163  cmp     dword ptr [rbx+1Ch], 0
0x180005167  jz      short loc_180005189
0x180005169  mov     eax, [rbx+8]
0x18000516c  lea     rdx, [rbx+20h]
0x180005170  lea     rcx, ds:0[rax*8]
0x180005178  shl     eax, 4
0x18000517b  add     rdx, rcx; Src
0x18000517e  mov     r8d, eax; Size
0x180005181  add     rcx, rbp; void *
0x180005184  call    memcpy_0
0x180005189  xor     ecx, ecx; dwErrCode
0x18000518b  call    cs:__imp_SetLastError
0x180005191  mov     ecx, [rsi+468h]; idThread
0x180005197  xor     r9d, r9d; lParam
0x18000519a  mov     r8, rdi; wParam
0x18000519d  mov     edx, 405h; Msg
0x1800051a2  call    cs:__imp_PostThreadMessageW
0x1800051a8  test    eax, eax
0x1800051aa  jnz     short loc_1800051E1
0x1800051ac  call    cs:__imp_GetLastError
0x1800051b2  mov     ebx, eax
0x1800051b4  test    eax, eax
0x1800051b6  jle     short loc_1800051C1
0x1800051b8  movzx   ebx, ax
0x1800051bb  or      ebx, 80070000h
0x1800051c1  test    ebx, ebx
0x1800051c3  mov     [rsp+58h+var_30], 0
0x1800051cc  mov     eax, 88980003h
0x1800051d1  mov     [rsp+58h+var_38], 0A94h
0x1800051d9  cmovns  ebx, eax
0x1800051dc  jmp     loc_1800050C8
0x1800051e1  xor     edi, edi
0x1800051e3  xor     ebx, ebx
0x1800051e5  mov     rcx, rdi; lpMem
0x1800051e8  call    ?Free@DefaultHeap@@SAXPEAX@Z; DefaultHeap::Free(void *)
0x1800051ed  mov     eax, ebx
0x1800051ef  add     rsp, 38h
0x1800051f3  pop     rdi
0x1800051f4  pop     rsi
0x1800051f5  pop     rbp
0x1800051f6  pop     rbx
0x1800051f7  retn
```
