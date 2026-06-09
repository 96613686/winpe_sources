# ATL::CComObject<ATL::CAxFrameWindow>::Release(void)

- ea: `0x140007a40`
- end: `0x140007a9b`
- name: `?Release@?$CComObject@VCAxFrameWindow@ATL@@@ATL@@UEAAKXZ`
- size: `91`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callees

- `0x140001008`
- `0x140002080`
- `0x140007a40`
- `0x14000c818`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<ATL::CAxFrameWindow>::Release(CExeModule *a1)
{
  int v1; // ebx
  unsigned int v2; // ebx
  _DWORD *v3; // rdi

  v1 = *((_DWORD *)a1 + 2);
  if ( v1 == 0x7FFFFFFF )
  {
    return 2147483646;
  }
  else
  {
    v2 = v1 - 1;
    *((_DWORD *)a1 + 2) = v2;
    if ( !v2 )
    {
      _InterlockedIncrement(&dword_1400153D8);
      v3 = (_DWORD *)((char *)a1 - 64);
      if ( a1 != (CExeModule *)64 )
      {
        ATL::CComObject<ATL::CAxFrameWindow>::~CComObject<ATL::CAxFrameWindow>((__int64)a1 - 64);
        operator delete(v3);
      }
      CExeModule::Unlock(a1);
    }
  }
  return v2;
}

```

## disassembly

```asm
0x140007a40  mov     [rsp+arg_0], rbx
0x140007a45  push    rdi
0x140007a46  sub     rsp, 20h
0x140007a4a  mov     ebx, [rcx+8]
0x140007a4d  cmp     ebx, 7FFFFFFFh
0x140007a53  jnz     short loc_140007A5C
0x140007a55  mov     ebx, 7FFFFFFEh
0x140007a5a  jmp     short loc_140007A8E
0x140007a5c  sub     ebx, 1
0x140007a5f  mov     [rcx+8], ebx
0x140007a62  jnz     short loc_140007A8E
0x140007a64  lock inc cs:dword_1400153D8
0x140007a6b  lea     rdi, [rcx-40h]
0x140007a6f  test    rdi, rdi
0x140007a72  jz      short loc_140007A89
0x140007a74  mov     rcx, rdi
0x140007a77  call    ??1?$CComObject@VCAxFrameWindow@ATL@@@ATL@@QEAA@XZ; ATL::CComObject<ATL::CAxFrameWindow>::~CComObject<ATL::CAxFrameWindow>(void)
0x140007a7c  mov     edx, 58h ; 'X'; unsigned __int64
0x140007a81  mov     rcx, rdi; void *
0x140007a84  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140007a89  call    ?Unlock@CExeModule@@QEAAJXZ; CExeModule::Unlock(void)
0x140007a8e  mov     eax, ebx
0x140007a90  mov     rbx, [rsp+28h+arg_0]
0x140007a95  add     rsp, 20h
0x140007a99  pop     rdi
0x140007a9a  retn
```
