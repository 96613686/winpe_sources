# CMemStreamBuffer::Release(void)

- ea: `0x180020e5c`
- end: `0x180020ef1`
- name: `?Release@CMemStreamBuffer@@QEAAIXZ`
- size: `149`
- prototype: `unsigned int __fastcall(CMemStreamBuffer *__hidden this)`
- caller_count: `4`
- callee_count: `4`
- tags: `file_ops, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180020dd0`
- `0x1800369c4`
- `0x18003acdc`
- `0x18005dd3c`

## callees

- `0x18000ddd4`
- `0x180020e5c`
- `0x18004d37c`
- `0x180066cfc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180020eaf`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180020eaf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180020e92`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180020e92`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180020ee9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180020ee9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180020e9c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180020e9c`

## pseudocode

```c
__int64 __fastcall CMemStreamBuffer::Release(CMemStreamBuffer *this)
{
  __int64 result; // rax
  _BYTE *v3; // rax
  __int64 v4; // rcx

  result = (unsigned int)_InterlockedDecrement((volatile signed __int32 *)this);
  if ( !(_DWORD)result )
  {
    if ( *((_QWORD *)this + 4) )
    {
      CMemStreamBuffer::WriteToReg(this);
      RegCloseKey(*((HKEY *)this + 4));
    }
    v3 = (_BYTE *)*((_QWORD *)this + 1);
    if ( v3 && !*((_QWORD *)this + 11) )
    {
      if ( (*((_BYTE *)this + 28) & 1) != 0 )
      {
        v4 = *((unsigned int *)this + 4);
        if ( *((_DWORD *)this + 4) )
        {
          do
          {
            *v3++ = 0;
            --v4;
          }
          while ( v4 );
        }
      }
      LocalFree(*((HLOCAL *)this + 1));
    }
    CoTaskMemFree(*((LPVOID *)this + 5));
    Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::InternalRelease((char *)this + 88);
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
    operator delete(this, (const struct std::nothrow_t *)0x60);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180020e5c  push    rbx
0x180020e5e  sub     rsp, 20h
0x180020e62  mov     rbx, rcx
0x180020e65  or      eax, 0FFFFFFFFh
0x180020e68  lock xadd [rcx], eax
0x180020e6c  sub     eax, 1
0x180020e6f  jnz     short loc_180020EC4
0x180020e71  cmp     qword ptr [rcx+20h], 0
0x180020e76  jnz     short loc_180020EE0
0x180020e78  mov     rax, [rbx+8]
0x180020e7c  test    rax, rax
0x180020e7f  jz      short loc_180020E98
0x180020e81  cmp     qword ptr [rbx+58h], 0
0x180020e86  jnz     short loc_180020E98
0x180020e88  test    byte ptr [rbx+1Ch], 1
0x180020e8c  jnz     short loc_180020ECA
0x180020e8e  mov     rcx, [rbx+8]; hMem
0x180020e92  call    cs:__imp_LocalFree
0x180020e98  mov     rcx, [rbx+28h]; pv
0x180020e9c  call    cs:__imp_CoTaskMemFree
0x180020ea2  lea     rcx, [rbx+58h]
0x180020ea6  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::InternalRelease(void)
0x180020eab  lea     rcx, [rbx+30h]; lpCriticalSection
0x180020eaf  call    cs:__imp_DeleteCriticalSection
0x180020eb5  mov     edx, 60h ; '`'; struct std::nothrow_t *
0x180020eba  mov     rcx, rbx; void *
0x180020ebd  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180020ec2  xor     eax, eax
0x180020ec4  add     rsp, 20h
0x180020ec8  pop     rbx
0x180020ec9  retn
0x180020eca  mov     ecx, [rbx+10h]
0x180020ecd  test    rcx, rcx
0x180020ed0  jz      short loc_180020E8E
0x180020ed2  mov     byte ptr [rax], 0
0x180020ed5  inc     rax
0x180020ed8  sub     rcx, 1; this
0x180020edc  jnz     short loc_180020ED2
0x180020ede  jmp     short loc_180020E8E
0x180020ee0  call    ?WriteToReg@CMemStreamBuffer@@AEAAHXZ; CMemStreamBuffer::WriteToReg(void)
0x180020ee5  mov     rcx, [rbx+20h]; hKey
0x180020ee9  call    cs:__imp_RegCloseKey
0x180020eef  jmp     short loc_180020E78
```
