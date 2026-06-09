# IStream_ReadPidl

- ea: `0x18000a4d0`
- end: `0x18000a5b2`
- name: `IStream_ReadPidl`
- size: `226`
- prototype: `HRESULT __stdcall(IStream *pstm, LPITEMIDLIST *ppidlOut)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x180003d44`
- `0x18000a4d0`
- `0x18000a5b8`
- `0x180012550`
- `0x180013066`

## import_xrefs

- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x18000a50b`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x18000a555`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x18000a50b`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x18000a555`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a582`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a582`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000a527`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000a527`

## pseudocode

```c
HRESULT __stdcall IStream_ReadPidl(IStream *pstm, LPITEMIDLIST *ppidlOut)
{
  int v4; // ebx
  ITEMIDLIST *v5; // rax
  ITEMIDLIST *v6; // rdi
  size_t v7; // rax
  UINT pv; // [rsp+20h] [rbp-28h] BYREF

  *ppidlOut = 0;
  pv = 0;
  v4 = IStream_Read(pstm, &pv, 4u);
  if ( v4 >= 0 )
  {
    if ( pv - 2 > 0xFFFD )
    {
      return -2147024883;
    }
    else
    {
      v5 = (ITEMIDLIST *)CoTaskMemAlloc(pv);
      v6 = v5;
      if ( v5 )
      {
        v7 = CTCoAllocPolicy::_CoTaskMemSize(v5);
        memset_0(v6, 0, v7);
        v4 = IStream_Read(pstm, v6, pv);
        if ( v4 >= 0 )
        {
          if ( IDListContainerIsConsistent(v6, pv) )
          {
            *ppidlOut = v6;
            v6 = 0;
            v4 = 0;
          }
          else
          {
            v4 = -2147024883;
          }
        }
        CoTaskMemFree(v6);
      }
      else
      {
        return -2147024882;
      }
    }
  }
  return v4;
}

```

## disassembly

```asm
0x18000a4d0  mov     [rsp+arg_10], rbx
0x18000a4d5  push    rbp
0x18000a4d6  push    rsi
0x18000a4d7  push    rdi
0x18000a4d8  sub     rsp, 30h
0x18000a4dc  mov     rax, cs:__security_cookie
0x18000a4e3  xor     rax, rsp
0x18000a4e6  mov     [rsp+48h+var_20], rax
0x18000a4eb  mov     rsi, rdx
0x18000a4ee  mov     qword ptr [rdx], 0
0x18000a4f5  lea     rdx, [rsp+48h+pv]; pv
0x18000a4fa  mov     [rsp+48h+pv], 0
0x18000a502  mov     r8d, 4; cb
0x18000a508  mov     rbp, rcx
0x18000a50b  call    cs:__imp_IStream_Read
0x18000a511  mov     ebx, eax
0x18000a513  test    eax, eax
0x18000a515  js      short loc_18000A596
0x18000a517  mov     edx, [rsp+48h+pv]
0x18000a51b  lea     eax, [rdx-2]
0x18000a51e  cmp     eax, 0FFFDh
0x18000a523  ja      short loc_18000A591
0x18000a525  mov     ecx, edx; cb
0x18000a527  call    cs:__imp_CoTaskMemAlloc
0x18000a52d  mov     rdi, rax
0x18000a530  test    rax, rax
0x18000a533  jz      short loc_18000A58A
0x18000a535  mov     rcx, rax; void *
0x18000a538  call    ?_CoTaskMemSize@CTCoAllocPolicy@@CA_KPEAX@Z; CTCoAllocPolicy::_CoTaskMemSize(void *)
0x18000a53d  mov     r8, rax; Size
0x18000a540  xor     edx, edx; Val
0x18000a542  mov     rcx, rdi; void *
0x18000a545  call    memset_0
0x18000a54a  mov     r8d, [rsp+48h+pv]; cb
0x18000a54f  mov     rdx, rdi; pv
0x18000a552  mov     rcx, rbp; pstm
0x18000a555  call    cs:__imp_IStream_Read
0x18000a55b  mov     ebx, eax
0x18000a55d  test    eax, eax
0x18000a55f  js      short loc_18000A57F
0x18000a561  mov     edx, [rsp+48h+pv]; cbAlloc
0x18000a565  mov     rcx, rdi; pidl
0x18000a568  call    IDListContainerIsConsistent
0x18000a56d  test    eax, eax
0x18000a56f  jz      short loc_18000A57A
0x18000a571  mov     [rsi], rdi
0x18000a574  xor     edi, edi
0x18000a576  xor     ebx, ebx
0x18000a578  jmp     short loc_18000A57F
0x18000a57a  mov     ebx, 8007000Dh
0x18000a57f  mov     rcx, rdi; pv
0x18000a582  call    cs:__imp_CoTaskMemFree
0x18000a588  jmp     short loc_18000A596
0x18000a58a  mov     ebx, 8007000Eh
0x18000a58f  jmp     short loc_18000A596
0x18000a591  mov     ebx, 8007000Dh
0x18000a596  mov     eax, ebx
0x18000a598  mov     rcx, [rsp+48h+var_20]
0x18000a59d  xor     rcx, rsp; StackCookie
0x18000a5a0  call    __security_check_cookie
0x18000a5a5  mov     rbx, [rsp+48h+arg_10]
0x18000a5aa  add     rsp, 30h
0x18000a5ae  pop     rdi
0x18000a5af  pop     rsi
0x18000a5b0  pop     rbp
0x18000a5b1  retn
```
