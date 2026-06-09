# mmioInternalInstallIOProc

- ea: `0x180011c1c`
- end: `0x180011d0e`
- name: `mmioInternalInstallIOProc`
- size: `242`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x180011ee0`
- `0x180011f00`

## callees

- `0x18000aef0`
- `0x18000e0d0`
- `0x1800119dc`
- `0x180011c1c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180011c35`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180011c35`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011c6d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011c6d`

## pseudocode

```c
__int64 __fastcall mmioInternalInstallIOProc(unsigned int a1, __int64 a2, int a3)
{
  DWORD CurrentThreadId; // eax
  __int64 v7; // rbp
  __int64 v8; // rbx
  __int64 result; // rax
  char *v10; // rcx
  char *v11; // rax
  __int64 v12; // rbx
  __int64 IOProc; // rax

  if ( !a1 )
    return 0;
  CurrentThreadId = GetCurrentThreadId();
  v7 = CurrentThreadId;
  if ( (a3 & 0x10000) != 0 )
  {
    if ( a2 )
    {
      v8 = NewHandle(5, 0, 32);
      if ( v8 )
      {
        LeaveCriticalSection(&HandleListCritSec);
        result = a2;
        *(_QWORD *)(v8 + 24) = off_18002C040;
        *(_DWORD *)v8 = a1;
        *(_QWORD *)(v8 + 8) = a2;
        *(_QWORD *)(v8 + 16) = v7;
        off_18002C040 = (char *)v8;
        return result;
      }
    }
    return 0;
  }
  if ( a2 )
    return 0;
  if ( (a3 & 0x20000) == 0 )
  {
    if ( (a3 & 0x40000) != 0 )
    {
      IOProc = FindIOProc(a1, CurrentThreadId);
      if ( IOProc )
        return *(_QWORD *)(IOProc + 8);
    }
    return 0;
  }
  v10 = off_18002C040;
  v11 = 0;
  while ( 1 )
  {
    if ( !v10 )
      return 0;
    if ( *(_DWORD *)v10 == a1 && *((_QWORD *)v10 + 2) == v7 )
      break;
    v11 = v10;
    v10 = (char *)*((_QWORD *)v10 + 3);
  }
  v12 = *((_QWORD *)v10 + 1);
  if ( v11 )
    *((_QWORD *)v11 + 3) = *((_QWORD *)v10 + 3);
  else
    off_18002C040 = (char *)*((_QWORD *)v10 + 3);
  FreeHandle(v10);
  return v12;
}

```

## disassembly

```asm
0x180011c1c  push    rbx
0x180011c1e  push    rbp
0x180011c1f  push    rsi
0x180011c20  push    rdi
0x180011c21  sub     rsp, 28h
0x180011c25  mov     ebx, r8d
0x180011c28  mov     rdi, rdx
0x180011c2b  mov     esi, ecx
0x180011c2d  test    ecx, ecx
0x180011c2f  jz      loc_180011D03
0x180011c35  call    cs:__imp_GetCurrentThreadId
0x180011c3b  mov     ebp, eax
0x180011c3d  bt      ebx, 10h
0x180011c41  jnb     short loc_180011C94
0x180011c43  test    rdi, rdi
0x180011c46  jz      loc_180011D03
0x180011c4c  xor     edx, edx
0x180011c4e  lea     ecx, [rdx+5]
0x180011c51  lea     r8d, [rdx+20h]
0x180011c55  call    NewHandle
0x180011c5a  mov     rbx, rax
0x180011c5d  test    rax, rax
0x180011c60  jz      loc_180011D03
0x180011c66  lea     rcx, HandleListCritSec; lpCriticalSection
0x180011c6d  call    cs:__imp_LeaveCriticalSection
0x180011c73  mov     rcx, cs:off_18002C040; "DOS "
0x180011c7a  mov     rax, rdi
0x180011c7d  mov     [rbx+18h], rcx
0x180011c81  mov     [rbx], esi
0x180011c83  mov     [rbx+8], rdi
0x180011c87  mov     [rbx+10h], rbp
0x180011c8b  mov     cs:off_18002C040, rbx; "DOS "
0x180011c92  jmp     short loc_180011D05
0x180011c94  test    rdi, rdi
0x180011c97  jnz     short loc_180011D03
0x180011c99  bt      ebx, 11h
0x180011c9d  jnb     short loc_180011CE8
0x180011c9f  mov     rcx, cs:off_18002C040; "DOS "
0x180011ca6  xor     eax, eax
0x180011ca8  test    rcx, rcx
0x180011cab  jz      short loc_180011CE1
0x180011cad  cmp     [rcx], esi
0x180011caf  jnz     short loc_180011CB7
0x180011cb1  cmp     [rcx+10h], rbp
0x180011cb5  jz      short loc_180011CC0
0x180011cb7  mov     rax, rcx
0x180011cba  mov     rcx, [rcx+18h]
0x180011cbe  jmp     short loc_180011CA8
0x180011cc0  mov     rbx, [rcx+8]
0x180011cc4  mov     rdx, [rcx+18h]
0x180011cc8  test    rax, rax
0x180011ccb  jz      short loc_180011CD3
0x180011ccd  mov     [rax+18h], rdx
0x180011cd1  jmp     short loc_180011CDA
0x180011cd3  mov     cs:off_18002C040, rdx; "DOS "
0x180011cda  call    FreeHandle
0x180011cdf  jmp     short loc_180011CE3
0x180011ce1  xor     ebx, ebx
0x180011ce3  mov     rax, rbx
0x180011ce6  jmp     short loc_180011D05
0x180011ce8  bt      ebx, 12h
0x180011cec  jnb     short loc_180011D03
0x180011cee  mov     rdx, rbp
0x180011cf1  mov     ecx, esi
0x180011cf3  call    FindIOProc
0x180011cf8  test    rax, rax
0x180011cfb  jz      short loc_180011D03
0x180011cfd  mov     rax, [rax+8]
0x180011d01  jmp     short loc_180011D05
0x180011d03  xor     eax, eax
0x180011d05  add     rsp, 28h
0x180011d09  pop     rdi
0x180011d0a  pop     rsi
0x180011d0b  pop     rbp
0x180011d0c  pop     rbx
0x180011d0d  retn
```
