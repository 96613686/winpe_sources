# HandlePortsChangedBroadcast

- ea: `0x180002f3c`
- end: `0x18000310d`
- name: `HandlePortsChangedBroadcast`
- size: `465`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180002230`

## callees

- `0x180002f3c`
- `0x1800138c5`

## import_xrefs

- `KERNELBASE!LocalAlloc` at `0x180002fa9`
- `KERNELBASE!LocalAlloc` at `0x180002fa9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800030f3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800030f3`
- `win32u!NtUserSetInformationThread` at `0x1800030a1`
- `win32u!NtUserSetInformationThread` at `0x1800030e4`
- `win32u!NtUserSetInformationThread` at `0x1800030a1`
- `win32u!NtUserSetInformationThread` at `0x1800030e4`
- `USER32!BroadcastSystemMessageW` at `0x1800030ca`
- `USER32!BroadcastSystemMessageW` at `0x1800030ca`

## pseudocode

```c
char *__fastcall HandlePortsChangedBroadcast(_QWORD *a1)
{
  char *v1; // rdi
  char *result; // rax
  __int64 v4; // rcx
  __int64 v5; // rbp
  char *lParam; // rsi
  unsigned __int64 v7; // r8
  _WORD *v8; // rdx
  __int64 v9; // rax
  _WORD *v10; // rcx
  WPARAM v11; // rbx
  __int128 v12; // [rsp+30h] [rbp-58h] BYREF
  __int64 v13; // [rsp+40h] [rbp-48h]
  DWORD Info; // [rsp+90h] [rbp+8h] BYREF

  v1 = (char *)(a1 + 2);
  result = 0;
  Info = 0;
  v12 = 0;
  v13 = 0;
  if ( a1 != (_QWORD *)-16LL )
  {
    v4 = 16;
    result = v1;
    do
    {
      if ( !*(_WORD *)result )
        break;
      result += 2;
      --v4;
    }
    while ( v4 );
    if ( v4 )
    {
      v5 = (2 * (16 - v4)) & -(__int64)(v4 != 0);
      result = (char *)LocalAlloc(0, v5 + 16);
      lParam = result;
      if ( result )
      {
        memset_0(result, 0, v5 + 16);
        *(_QWORD *)(lParam + 4) = 3;
        v7 = (unsigned __int64)(v5 + 2) >> 1;
        *(_DWORD *)lParam = v5 + 16;
        if ( v7 )
        {
          v8 = lParam + 12;
          if ( v7 <= 0x7FFFFFFF )
          {
            v9 = 2147483646;
            do
            {
              if ( !v9 )
                break;
              if ( !*(_WORD *)v1 )
                break;
              *v8 = *(_WORD *)v1;
              v1 += 2;
              ++v8;
              --v9;
              --v7;
            }
            while ( v7 );
            v10 = v8 - 1;
            if ( v7 )
              v10 = v8;
            *v10 = 0;
            if ( !v7 )
              return (char *)LocalFree(lParam);
            if ( *a1 == *(_QWORD *)&GUID_DEVICE_INTERFACE_ARRIVAL.Data1
              && a1[1] == *(_QWORD *)GUID_DEVICE_INTERFACE_ARRIVAL.Data4 )
            {
              v11 = 0x8000;
            }
            else
            {
              if ( *a1 != *(_QWORD *)&GUID_DEVICE_INTERFACE_REMOVAL.Data1
                || a1[1] != *(_QWORD *)GUID_DEVICE_INTERFACE_REMOVAL.Data4 )
              {
                return (char *)LocalFree(lParam);
              }
              v11 = 32772;
            }
            Info = 16;
            if ( (int)NtUserSetInformationThread(-2, 7, &v12) >= 0 )
            {
              BroadcastSystemMessageW(0x20u, &Info, 0x219u, v11, (LPARAM)lParam);
              NtUserSetInformationThread(-2, 9, &v12);
            }
          }
          else
          {
            *v8 = 0;
          }
        }
        return (char *)LocalFree(lParam);
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180002f3c  mov     r11, rsp
0x180002f3f  push    rbx
0x180002f40  push    rbp
0x180002f41  push    rsi
0x180002f42  push    rdi
0x180002f43  push    r14
0x180002f45  push    r15
0x180002f47  sub     rsp, 58h
0x180002f4b  xor     r15d, r15d
0x180002f4e  lea     rdi, [rcx+10h]
0x180002f52  xor     eax, eax
0x180002f54  mov     [r11+8], r15d
0x180002f58  xorps   xmm0, xmm0
0x180002f5b  mov     rbx, rcx
0x180002f5e  movups  [rsp+88h+var_58], xmm0
0x180002f63  mov     [r11-48h], rax
0x180002f67  test    rdi, rdi
0x180002f6a  jz      loc_1800030FF
0x180002f70  lea     ecx, [rax+10h]
0x180002f73  mov     rax, rdi
0x180002f76  cmp     [rax], r15w
0x180002f7a  jz      short loc_180002F86
0x180002f7c  add     rax, 2
0x180002f80  sub     rcx, 1
0x180002f84  jnz     short loc_180002F76
0x180002f86  test    rcx, rcx
0x180002f89  jz      loc_1800030FF
0x180002f8f  mov     eax, 10h
0x180002f94  sub     rax, rcx
0x180002f97  add     rax, rax
0x180002f9a  neg     rcx
0x180002f9d  sbb     rbp, rbp
0x180002fa0  xor     ecx, ecx; uFlags
0x180002fa2  and     rbp, rax
0x180002fa5  lea     rdx, [rbp+10h]; uBytes
0x180002fa9  call    cs:__imp_LocalAlloc
0x180002fb0  nop     dword ptr [rax+rax+00h]
0x180002fb5  mov     rsi, rax
0x180002fb8  test    rax, rax
0x180002fbb  jz      loc_1800030FF
0x180002fc1  lea     r8, [rbp+10h]; Size
0x180002fc5  xor     edx, edx; Val
0x180002fc7  mov     rcx, rax; void *
0x180002fca  call    memset_0
0x180002fcf  lea     r8, [rbp+2]
0x180002fd3  mov     qword ptr [rsi+4], 3
0x180002fdb  shr     r8, 1
0x180002fde  lea     eax, [rbp+10h]
0x180002fe1  mov     [rsi], eax
0x180002fe3  jz      loc_1800030F0
0x180002fe9  lea     rdx, [rsi+0Ch]
0x180002fed  cmp     r8, 7FFFFFFFh
0x180002ff4  jbe     short loc_180002FFF
0x180002ff6  mov     [rdx], r15w
0x180002ffa  jmp     loc_1800030F0
0x180002fff  mov     eax, 7FFFFFFEh
0x180003004  test    rax, rax
0x180003007  jz      short loc_180003025
0x180003009  movzx   ecx, word ptr [rdi]
0x18000300c  test    cx, cx
0x18000300f  jz      short loc_180003025
0x180003011  mov     [rdx], cx
0x180003014  add     rdi, 2
0x180003018  add     rdx, 2
0x18000301c  dec     rax
0x18000301f  sub     r8, 1
0x180003023  jnz     short loc_180003004
0x180003025  test    r8, r8
0x180003028  lea     rcx, [rdx-2]
0x18000302c  cmovnz  rcx, rdx
0x180003030  mov     [rcx], r15w
0x180003034  jz      loc_1800030F0
0x18000303a  mov     rax, [rbx]
0x18000303d  cmp     rax, qword ptr cs:GUID_DEVICE_INTERFACE_ARRIVAL.Data1
0x180003044  jnz     short loc_18000305A
0x180003046  mov     rax, [rbx+8]
0x18000304a  cmp     rax, qword ptr cs:GUID_DEVICE_INTERFACE_ARRIVAL.Data4
0x180003051  jnz     short loc_18000305A
0x180003053  mov     ebx, 8000h
0x180003058  jmp     short loc_18000307C
0x18000305a  mov     rax, [rbx]
0x18000305d  cmp     rax, qword ptr cs:GUID_DEVICE_INTERFACE_REMOVAL.Data1
0x180003064  jnz     loc_1800030F0
0x18000306a  mov     rax, [rbx+8]
0x18000306e  cmp     rax, qword ptr cs:GUID_DEVICE_INTERFACE_REMOVAL.Data4
0x180003075  jnz     short loc_1800030F0
0x180003077  mov     ebx, 8004h
0x18000307c  mov     edi, 18h
0x180003081  mov     [rsp+88h+Info], 10h
0x18000308c  mov     rbp, 0FFFFFFFFFFFFFFFEh
0x180003093  lea     r8, [rsp+88h+var_58]
0x180003098  mov     r9d, edi
0x18000309b  mov     rcx, rbp
0x18000309e  lea     edx, [rdi-11h]
0x1800030a1  call    cs:__imp_NtUserSetInformationThread
0x1800030a8  nop     dword ptr [rax+rax+00h]
0x1800030ad  test    eax, eax
0x1800030af  js      short loc_1800030F0
0x1800030b1  mov     r9, rbx; wParam
0x1800030b4  mov     [rsp+88h+lParam], rsi; lParam
0x1800030b9  mov     r8d, 219h; Msg
0x1800030bf  lea     rdx, [rsp+88h+Info]; lpInfo
0x1800030c7  lea     ecx, [rdi+8]; flags
0x1800030ca  call    cs:__imp_BroadcastSystemMessageW
0x1800030d1  nop     dword ptr [rax+rax+00h]
0x1800030d6  mov     r9d, edi
0x1800030d9  lea     r8, [rsp+88h+var_58]
0x1800030de  lea     edx, [rdi-0Fh]
0x1800030e1  mov     rcx, rbp
0x1800030e4  call    cs:__imp_NtUserSetInformationThread
0x1800030eb  nop     dword ptr [rax+rax+00h]
0x1800030f0  mov     rcx, rsi; hMem
0x1800030f3  call    cs:__imp_LocalFree
0x1800030fa  nop     dword ptr [rax+rax+00h]
0x1800030ff  add     rsp, 58h
0x180003103  pop     r15
0x180003105  pop     r14
0x180003107  pop     rdi
0x180003108  pop     rsi
0x180003109  pop     rbp
0x18000310a  pop     rbx
0x18000310b  retn
```
