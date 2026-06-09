# WerpAuxmdDumpRegisteredBlocks

- ea: `0x180005810`
- end: `0x180005a7d`
- name: `WerpAuxmdDumpRegisteredBlocks`
- size: `621`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180005810`
- `0x180005a84`
- `0x18000716c`
- `0x18002c220`
- `0x180040c34`
- `0x18006c7b4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800058a6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800059ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800058a6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800059ec`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18000589c`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x1800059e2`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18000589c`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x1800059e2`

## pseudocode

```c
__int64 __fastcall WerpAuxmdDumpRegisteredBlocks(__int64 a1)
{
  void *v1; // rdi
  unsigned int v3; // r12d
  int GatherListStart; // eax
  __int64 v5; // rbx
  int v6; // eax
  DWORD LastError; // eax
  __int64 v8; // rdx
  __int64 v9; // rax
  __int64 v10; // r8
  void *v11; // rdi
  DWORD v12; // eax
  __int128 Buffer; // [rsp+40h] [rbp-20h] BYREF
  __int128 v15; // [rsp+50h] [rbp-10h]
  LPCVOID lpBaseAddress; // [rsp+B0h] [rbp+50h] BYREF
  SIZE_T NumberOfBytesRead; // [rsp+B8h] [rbp+58h] BYREF

  v1 = *(void **)a1;
  v3 = 0;
  lpBaseAddress = 0;
  NumberOfBytesRead = 0;
  Buffer = 0;
  v15 = 0;
  GatherListStart = WerpGetGatherListStart(v1, (struct WER_GATHER **)&lpBaseAddress);
  v5 = (__int64)lpBaseAddress;
  if ( GatherListStart >= 0 )
  {
    if ( lpBaseAddress )
    {
      if ( lpBaseAddress == (LPCVOID)-1LL )
      {
        v6 = -2147024637;
      }
      else if ( ReadProcessMemory(v1, lpBaseAddress, &Buffer, 0x20u, &NumberOfBytesRead) )
      {
        if ( NumberOfBytesRead == 32 )
        {
          v5 = Buffer;
          if ( !(_QWORD)Buffer )
            v5 = -1;
          v6 = 0;
          lpBaseAddress = (LPCVOID)v5;
        }
        else
        {
          v6 = -2147024597;
        }
      }
      else
      {
        LastError = GetLastError();
        v6 = ERROR_HR_FROM_WIN32(LastError);
      }
    }
    else
    {
      v6 = -2147023728;
    }
    while ( 1 )
    {
      if ( v6 < 0 )
        goto LABEL_34;
      if ( (WORD4(Buffer) & 0xC000) == 0 && DWORD2(v15) <= 0x10000 )
      {
        v8 = *(unsigned int *)(a1 + 44);
        v9 = v8 + DWORD2(v15);
        v10 = ~(v8 - 1);
        if ( (v10 & (unsigned __int64)(v9 + v15 - 1)) > ((unsigned __int64)v15 & v10) )
        {
          WerpAuxmdpDumpRegisteredBlock(a1, v10 & (v9 + v15 - 1));
          ++v3;
          if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 8) != 0 )
            WPP_SF_DDDDD(*((_QWORD *)WPP_GLOBAL_Control + 2));
        }
      }
      v11 = *(void **)a1;
      NumberOfBytesRead = 0;
      Buffer = 0;
      v15 = 0;
      if ( v5 )
        break;
      v6 = WerpGetGatherListStart(v11, (struct WER_GATHER **)&lpBaseAddress);
      v5 = (__int64)lpBaseAddress;
      if ( v6 >= 0 )
      {
        if ( lpBaseAddress )
          break;
        v6 = -2147023728;
      }
LABEL_33:
      if ( v3 >= 0x200 )
        goto LABEL_34;
    }
    if ( v5 == -1 )
    {
      v6 = -2147024637;
    }
    else if ( ReadProcessMemory(v11, (LPCVOID)v5, &Buffer, 0x20u, &NumberOfBytesRead) )
    {
      if ( NumberOfBytesRead == 32 )
      {
        v5 = Buffer;
        if ( !(_QWORD)Buffer )
          v5 = -1;
        v6 = 0;
        lpBaseAddress = (LPCVOID)v5;
      }
      else
      {
        v6 = -2147024597;
      }
    }
    else
    {
      v12 = GetLastError();
      v6 = ERROR_HR_FROM_WIN32(v12);
    }
    goto LABEL_33;
  }
LABEL_34:
  *(_DWORD *)(a1 + 4160) = v3;
  *(_DWORD *)(a1 + 4164) = 0;
  if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 8) != 0 )
    WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, WPP_78df9e3b89b83f0cbcd64e4857b7b890_Traceguids, 0, v3);
  return 0;
}

```

## disassembly

```asm
0x180005810  push    rbp
0x180005812  push    rbx
0x180005813  push    rsi
0x180005814  push    rdi
0x180005815  push    r12
0x180005817  push    r14
0x180005819  push    r15
0x18000581b  mov     rbp, rsp
0x18000581e  sub     rsp, 60h
0x180005822  mov     rdi, [rcx]
0x180005825  lea     rdx, [rbp+lpBaseAddress]; struct WER_GATHER **
0x180005829  xorps   xmm0, xmm0
0x18000582c  mov     [rbp+arg_8], 0
0x180005833  mov     r15, rcx
0x180005836  mov     [rbp+arg_0], 0
0x18000583d  xor     r14d, r14d
0x180005840  xor     r12d, r12d
0x180005843  mov     rcx, rdi; void *
0x180005846  mov     [rbp+lpBaseAddress], r14
0x18000584a  mov     [rbp+NumberOfBytesRead], r12
0x18000584e  movups  [rbp+Buffer], xmm0
0x180005852  movups  [rbp+var_10], xmm0
0x180005856  call    ?WerpGetGatherListStart@@YAJPEAXPEAPEAUWER_GATHER@@@Z; WerpGetGatherListStart(void *,WER_GATHER * *)
0x18000585b  mov     rbx, [rbp+lpBaseAddress]
0x18000585f  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180005863  test    eax, eax
0x180005865  js      loc_180005A27
0x18000586b  test    rbx, rbx
0x18000586e  jnz     short loc_180005877
0x180005870  mov     eax, 80070490h
0x180005875  jmp     short loc_1800058D4
0x180005877  cmp     rbx, rsi
0x18000587a  jnz     short loc_180005883
0x18000587c  mov     eax, 80070103h
0x180005881  jmp     short loc_1800058D4
0x180005883  lea     rax, [rbp+NumberOfBytesRead]
0x180005887  mov     r9d, 20h ; ' '; nSize
0x18000588d  lea     r8, [rbp+Buffer]; lpBuffer
0x180005891  mov     [rsp+60h+lpNumberOfBytesRead], rax; lpNumberOfBytesRead
0x180005896  mov     rdx, rbx; lpBaseAddress
0x180005899  mov     rcx, rdi; hProcess
0x18000589c  call    cs:__imp_ReadProcessMemory
0x1800058a2  test    eax, eax
0x1800058a4  jnz     short loc_1800058B5
0x1800058a6  call    cs:__imp_GetLastError
0x1800058ac  mov     ecx, eax; unsigned int
0x1800058ae  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x1800058b3  jmp     short loc_1800058D4
0x1800058b5  cmp     [rbp+NumberOfBytesRead], 20h ; ' '
0x1800058ba  jz      short loc_1800058C3
0x1800058bc  mov     eax, 8007012Bh
0x1800058c1  jmp     short loc_1800058D4
0x1800058c3  mov     rbx, qword ptr [rbp+Buffer]
0x1800058c7  test    rbx, rbx
0x1800058ca  cmovz   rbx, rsi
0x1800058ce  xor     eax, eax
0x1800058d0  mov     [rbp+lpBaseAddress], rbx
0x1800058d4  test    eax, eax
0x1800058d6  js      loc_180005A27
0x1800058dc  mov     eax, 0C000h
0x1800058e1  test    word ptr [rbp+Buffer+8], ax
0x1800058e5  jnz     loc_180005982
0x1800058eb  cmp     dword ptr [rbp+var_10+8], 10000h
0x1800058f2  ja      loc_180005982
0x1800058f8  mov     edx, [r15+2Ch]
0x1800058fc  mov     rcx, qword ptr [rbp+var_10]
0x180005900  mov     eax, dword ptr [rbp+var_10+8]
0x180005903  add     rax, rdx
0x180005906  lea     r8, [rdx-1]
0x18000590a  not     r8
0x18000590d  lea     rdi, [rcx-1]
0x180005911  add     rdi, rax
0x180005914  mov     rsi, r8
0x180005917  and     rsi, rcx
0x18000591a  and     rdi, r8
0x18000591d  cmp     rdi, rsi
0x180005920  jbe     short loc_18000597E
0x180005922  mov     r9, rsi
0x180005925  mov     [rsp+60h+lpNumberOfBytesRead], rdi; __int64
0x18000592a  lea     r8, [rbp+arg_8]
0x18000592e  mov     rcx, r15; int
0x180005931  lea     rdx, [rbp+arg_0]
0x180005935  call    WerpAuxmdpDumpRegisteredBlock
0x18000593a  mov     r9d, [rbp+arg_0]
0x18000593e  mov     edx, eax
0x180005940  add     r14d, r9d
0x180005943  inc     r12d
0x180005946  mov     rcx, cs:WPP_GLOBAL_Control
0x18000594d  lea     rax, WPP_GLOBAL_Control
0x180005954  cmp     rcx, rax
0x180005957  jz      short loc_18000597E
0x180005959  test    byte ptr [rcx+1Ch], 8
0x18000595d  jz      short loc_18000597E
0x18000595f  mov     eax, [rbp+arg_8]
0x180005962  sub     edi, esi
0x180005964  mov     rcx, [rcx+10h]
0x180005968  mov     [rsp+60h+var_28], eax
0x18000596c  mov     [rsp+60h+var_30], edx
0x180005970  mov     [rsp+60h+var_38], r12d
0x180005975  mov     dword ptr [rsp+60h+lpNumberOfBytesRead], edi
0x180005979  call    WPP_SF_DDDDD
0x18000597e  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180005982  mov     rdi, [r15]
0x180005985  xorps   xmm0, xmm0
0x180005988  mov     [rbp+NumberOfBytesRead], 0
0x180005990  movups  [rbp+Buffer], xmm0
0x180005994  movups  [rbp+var_10], xmm0
0x180005998  test    rbx, rbx
0x18000599b  jnz     short loc_1800059BD
0x18000599d  lea     rdx, [rbp+lpBaseAddress]; struct WER_GATHER **
0x1800059a1  mov     rcx, rdi; void *
0x1800059a4  call    ?WerpGetGatherListStart@@YAJPEAXPEAPEAUWER_GATHER@@@Z; WerpGetGatherListStart(void *,WER_GATHER * *)
0x1800059a9  mov     rbx, [rbp+lpBaseAddress]
0x1800059ad  test    eax, eax
0x1800059af  js      short loc_180005A1A
0x1800059b1  test    rbx, rbx
0x1800059b4  jnz     short loc_1800059BD
0x1800059b6  mov     eax, 80070490h
0x1800059bb  jmp     short loc_180005A1A
0x1800059bd  cmp     rbx, rsi
0x1800059c0  jnz     short loc_1800059C9
0x1800059c2  mov     eax, 80070103h
0x1800059c7  jmp     short loc_180005A1A
0x1800059c9  lea     rax, [rbp+NumberOfBytesRead]
0x1800059cd  mov     r9d, 20h ; ' '; nSize
0x1800059d3  lea     r8, [rbp+Buffer]; lpBuffer
0x1800059d7  mov     [rsp+60h+lpNumberOfBytesRead], rax; lpNumberOfBytesRead
0x1800059dc  mov     rdx, rbx; lpBaseAddress
0x1800059df  mov     rcx, rdi; hProcess
0x1800059e2  call    cs:__imp_ReadProcessMemory
0x1800059e8  test    eax, eax
0x1800059ea  jnz     short loc_1800059FB
0x1800059ec  call    cs:__imp_GetLastError
0x1800059f2  mov     ecx, eax; unsigned int
0x1800059f4  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x1800059f9  jmp     short loc_180005A1A
0x1800059fb  cmp     [rbp+NumberOfBytesRead], 20h ; ' '
0x180005a00  jz      short loc_180005A09
0x180005a02  mov     eax, 8007012Bh
0x180005a07  jmp     short loc_180005A1A
0x180005a09  mov     rbx, qword ptr [rbp+Buffer]
0x180005a0d  test    rbx, rbx
0x180005a10  cmovz   rbx, rsi
0x180005a14  xor     eax, eax
0x180005a16  mov     [rbp+lpBaseAddress], rbx
0x180005a1a  cmp     r12d, 200h
0x180005a21  jb      loc_1800058D4
0x180005a27  mov     [r15+1040h], r12d
0x180005a2e  mov     [r15+1044h], r14d
0x180005a35  mov     rcx, cs:WPP_GLOBAL_Control
0x180005a3c  lea     rax, WPP_GLOBAL_Control
0x180005a43  cmp     rcx, rax
0x180005a46  jz      short loc_180005A6B
0x180005a48  test    byte ptr [rcx+1Ch], 8
0x180005a4c  jz      short loc_180005A6B
0x180005a4e  mov     rcx, [rcx+10h]
0x180005a52  lea     r8, WPP_78df9e3b89b83f0cbcd64e4857b7b890_Traceguids
0x180005a59  mov     edx, 1Bh
0x180005a5e  mov     dword ptr [rsp+60h+lpNumberOfBytesRead], r12d
0x180005a63  mov     r9d, r14d
0x180005a66  call    WPP_SF_Dd
0x180005a6b  mov     eax, r14d
0x180005a6e  add     rsp, 60h
0x180005a72  pop     r15
0x180005a74  pop     r14
0x180005a76  pop     r12
0x180005a78  pop     rdi
0x180005a79  pop     rsi
0x180005a7a  pop     rbx
0x180005a7b  pop     rbp
0x180005a7c  retn
```
