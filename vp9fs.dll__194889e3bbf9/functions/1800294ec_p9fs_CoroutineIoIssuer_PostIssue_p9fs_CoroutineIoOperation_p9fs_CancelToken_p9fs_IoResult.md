# p9fs::CoroutineIoIssuer::PostIssue(p9fs::CoroutineIoOperation &,p9fs::CancelToken &,p9fs::IoResult)

- ea: `0x1800294ec`
- end: `0x180029542`
- name: `?PostIssue@CoroutineIoIssuer@p9fs@@AEAAXAEAUCoroutineIoOperation@2@AEAVCancelToken@2@UIoResult@2@@Z`
- size: `86`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180028b60`
- `0x180028c38`
- `0x180028d20`
- `0x180028e10`
- `0x180028ef4`

## callees

- `0x1800294ec`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x18002950d`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x18002950d`
- `api-ms-win-core-io-l1-1-0!CancelIoEx` at `0x180029534`
- `api-ms-win-core-io-l1-1-0!CancelIoEx` at `0x180029534`

## pseudocode

```c
char __fastcall p9fs::CoroutineIoIssuer::PostIssue(__int64 a1, __int64 a2, __int64 a3, unsigned __int64 a4)
{
  int v4; // ebx
  unsigned __int64 v5; // rsi
  char result; // al

  v4 = a4;
  v5 = HIDWORD(a4);
  if ( (_DWORD)a4 == 997 )
  {
    result = *(_BYTE *)(a3 + 88);
    if ( result )
      return CancelIoEx(*(HANDLE *)(a1 + 8), (LPOVERLAPPED)(a2 + 16));
  }
  else
  {
    CancelThreadpoolIo(*(PTP_IO *)a1);
    *(_DWORD *)(a2 + 48) = v4;
    *(_DWORD *)(a2 + 52) = v5;
    result = *(_BYTE *)(a2 + 64);
    *(_BYTE *)(a2 + 64) = 1;
  }
  return result;
}

```

## disassembly

```asm
0x1800294ec  push    rbx
0x1800294ee  push    rsi
0x1800294ef  push    rdi
0x1800294f0  sub     rsp, 20h
0x1800294f4  mov     rsi, r9
0x1800294f7  mov     rbx, r9
0x1800294fa  shr     rsi, 20h
0x1800294fe  mov     rdi, rdx
0x180029501  cmp     r9d, 3E5h
0x180029508  jz      short loc_180029523
0x18002950a  mov     rcx, [rcx]; pio
0x18002950d  call    cs:__imp_CancelThreadpoolIo
0x180029513  mov     eax, 1
0x180029518  mov     [rdi+30h], ebx
0x18002951b  mov     [rdi+34h], esi
0x18002951e  xchg    al, [rdi+40h]
0x180029521  jmp     short loc_18002953A
0x180029523  mov     al, [r8+58h]
0x180029527  nop
0x180029528  test    al, al
0x18002952a  jz      short loc_18002953A
0x18002952c  mov     rcx, [rcx+8]; hFile
0x180029530  add     rdx, 10h; lpOverlapped
0x180029534  call    cs:__imp_CancelIoEx
0x18002953a  add     rsp, 20h
0x18002953e  pop     rdi
0x18002953f  pop     rsi
0x180029540  pop     rbx
0x180029541  retn
```
