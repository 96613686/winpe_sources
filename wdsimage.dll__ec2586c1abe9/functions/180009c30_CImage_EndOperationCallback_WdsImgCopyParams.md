# CImage::EndOperationCallback(WdsImgCopyParams *)

- ea: `0x180009c30`
- end: `0x180009cae`
- name: `?EndOperationCallback@CImage@@SAJPEAUWdsImgCopyParams@@@Z`
- size: `126`
- prototype: `__int64 __fastcall(struct WdsImgCopyParams *)`
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x180008cc0`
- `0x180008e70`
- `0x1800092fc`
- `0x1800093d8`
- `0x18000c35c`

## callees

- `0x180009c30`
- `0x18000d5b0`
- `0x180011010`

## pseudocode

```c
__int64 __fastcall CImage::EndOperationCallback(struct WdsImgCopyParams *a1, __int64 a2)
{
  unsigned int v2; // edi
  __int64 v4; // rdx

  v2 = 0;
  if ( *((_QWORD *)a1 + 5) )
  {
    if ( !*((_DWORD *)a1 + 8)
      || (v2 = -2147023673, (int)ElValidateHr_5(2147943623LL, a2, "base\\eco\\wds\\wdsimage\\src\\image.cpp", 4016) >= 0) )
    {
      if ( (*((unsigned int (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD))a1 + 5))(3, 0, 0, *((_QWORD *)a1 + 6)) )
      {
        v2 = -2147023673;
        *((_DWORD *)a1 + 8) = 1;
        ElValidateHr_5(2147943623LL, v4, "base\\eco\\wds\\wdsimage\\src\\image.cpp", 4028);
      }
    }
  }
  return v2;
}

```

## disassembly

```asm
0x180009c30  mov     [rsp+arg_0], rbx
0x180009c35  push    rdi
0x180009c36  sub     rsp, 30h
0x180009c3a  xor     edi, edi
0x180009c3c  mov     rbx, rcx
0x180009c3f  cmp     [rcx+28h], rdi
0x180009c43  jz      short loc_180009CA0
0x180009c45  cmp     [rcx+20h], edi
0x180009c48  jz      short loc_180009C67
0x180009c4a  mov     edi, 800704C7h
0x180009c4f  lea     r8, aBaseEcoWdsWdsi_5; "base\\eco\\wds\\wdsimage\\src\\image.cp"...
0x180009c56  mov     ecx, edi
0x180009c58  mov     r9d, 0FB0h
0x180009c5e  call    ElValidateHr_5
0x180009c63  test    eax, eax
0x180009c65  js      short loc_180009CA0
0x180009c67  mov     r9, [rbx+30h]
0x180009c6b  xor     edx, edx
0x180009c6d  mov     rax, [rbx+28h]
0x180009c71  xor     r8d, r8d
0x180009c74  lea     ecx, [rdx+3]
0x180009c77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009c7c  test    eax, eax
0x180009c7e  jz      short loc_180009CA0
0x180009c80  mov     edi, 800704C7h
0x180009c85  mov     dword ptr [rbx+20h], 1
0x180009c8c  mov     ecx, edi
0x180009c8e  lea     r8, aBaseEcoWdsWdsi_5; "base\\eco\\wds\\wdsimage\\src\\image.cp"...
0x180009c95  mov     r9d, 0FBCh
0x180009c9b  call    ElValidateHr_5
0x180009ca0  mov     rbx, [rsp+38h+arg_0]
0x180009ca5  mov     eax, edi
0x180009ca7  add     rsp, 30h
0x180009cab  pop     rdi
0x180009cac  retn
```
