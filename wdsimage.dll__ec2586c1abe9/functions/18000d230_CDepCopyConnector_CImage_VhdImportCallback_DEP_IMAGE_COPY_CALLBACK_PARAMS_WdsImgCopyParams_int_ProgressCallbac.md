# CDepCopyConnector<&CImage::VhdImportCallback(_DEP_IMAGE_COPY_CALLBACK_PARAMS *,WdsImgCopyParams *,int *)>::_ProgressCallback(_LARGE_INTEGER,_LARGE_INTEGER,_LARGE_INTEGER,_LARGE_INTEGER,ulong,ulong,void *,void *,void *)

- ea: `0x18000d230`
- end: `0x18000d29a`
- name: `?_ProgressCallback@?$CDepCopyConnector@$1?VhdImportCallback@CImage@@QEAAJPEAU_DEP_IMAGE_COPY_CALLBACK_PARAMS@@PEAUWdsImgCopyParams@@PEAH@Z@@SAKT_LARGE_INTEGER@@000KKPEAX11@Z`
- size: `106`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000d230`
- `0x180011010`

## pseudocode

```c
__int64 __fastcall CDepCopyConnector<&public: long CImage::VhdImportCallback(_DEP_IMAGE_COPY_CALLBACK_PARAMS *,WdsImgCopyParams *,int *)>::_ProgressCallback(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        int a5,
        int a6,
        int a7,
        int a8,
        __int64 a9)
{
  unsigned int v9; // ebx
  __int64 v10; // rax

  v9 = 0;
  if ( *(_QWORD *)(a9 + 40) )
  {
    if ( *(_DWORD *)(a9 + 32) )
    {
      return 1;
    }
    else
    {
      if ( a1 )
        v10 = 100 * a2 / a1;
      else
        v10 = 100;
      if ( (*(unsigned int (__fastcall **)(__int64, __int64, _QWORD, _QWORD))(a9 + 40))(1, v10, 0, *(_QWORD *)(a9 + 48)) )
      {
        v9 = 1;
        *(_DWORD *)(a9 + 32) = 1;
      }
    }
  }
  return v9;
}

```

## disassembly

```asm
0x18000d230  mov     [rsp+arg_0], rbx
0x18000d235  push    rsi
0x18000d236  sub     rsp, 30h
0x18000d23a  mov     rsi, [rsp+38h+arg_40]
0x18000d242  xor     ebx, ebx
0x18000d244  cmp     [rsi+28h], rbx
0x18000d248  jz      short loc_18000D28C
0x18000d24a  cmp     [rsi+20h], ebx
0x18000d24d  jz      short loc_18000D256
0x18000d24f  mov     ebx, 1
0x18000d254  jmp     short loc_18000D28C
0x18000d256  test    rcx, rcx
0x18000d259  jnz     short loc_18000D260
0x18000d25b  lea     eax, [rcx+64h]
0x18000d25e  jmp     short loc_18000D269
0x18000d260  imul    rax, rdx, 64h ; 'd'
0x18000d264  cqo
0x18000d266  idiv    rcx
0x18000d269  mov     r9, [rsi+30h]
0x18000d26d  xor     r8d, r8d
0x18000d270  mov     rdx, rax
0x18000d273  mov     rax, [rsi+28h]
0x18000d277  lea     ecx, [r8+1]
0x18000d27b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d280  test    eax, eax
0x18000d282  jz      short loc_18000D28C
0x18000d284  mov     ebx, 1
0x18000d289  mov     [rsi+20h], ebx
0x18000d28c  mov     eax, ebx
0x18000d28e  mov     rbx, [rsp+38h+arg_0]
0x18000d293  add     rsp, 30h
0x18000d297  pop     rsi
0x18000d298  retn
```
