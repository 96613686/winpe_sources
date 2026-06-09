# ATL::CComObject<ATL::CAxUIWindow>::Release(void)

- ea: `0x140007ab0`
- end: `0x140007b0b`
- name: `?Release@?$CComObject@VCAxUIWindow@ATL@@@ATL@@UEAAKXZ`
- size: `91`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callees

- `0x140001008`
- `0x140002108`
- `0x140007ab0`
- `0x14000c818`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<ATL::CAxUIWindow>::Release(CExeModule *a1)
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
        ATL::CComObject<ATL::CAxUIWindow>::~CComObject<ATL::CAxUIWindow>((__int64)a1 - 64);
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
0x140007ab0  mov     [rsp+arg_0], rbx
0x140007ab5  push    rdi
0x140007ab6  sub     rsp, 20h
0x140007aba  mov     ebx, [rcx+8]
0x140007abd  cmp     ebx, 7FFFFFFFh
0x140007ac3  jnz     short loc_140007ACC
0x140007ac5  mov     ebx, 7FFFFFFEh
0x140007aca  jmp     short loc_140007AFE
0x140007acc  sub     ebx, 1
0x140007acf  mov     [rcx+8], ebx
0x140007ad2  jnz     short loc_140007AFE
0x140007ad4  lock inc cs:dword_1400153D8
0x140007adb  lea     rdi, [rcx-40h]
0x140007adf  test    rdi, rdi
0x140007ae2  jz      short loc_140007AF9
0x140007ae4  mov     rcx, rdi
0x140007ae7  call    ??1?$CComObject@VCAxUIWindow@ATL@@@ATL@@QEAA@XZ; ATL::CComObject<ATL::CAxUIWindow>::~CComObject<ATL::CAxUIWindow>(void)
0x140007aec  mov     edx, 58h ; 'X'; unsigned __int64
0x140007af1  mov     rcx, rdi; void *
0x140007af4  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140007af9  call    ?Unlock@CExeModule@@QEAAJXZ; CExeModule::Unlock(void)
0x140007afe  mov     eax, ebx
0x140007b00  mov     rbx, [rsp+28h+arg_0]
0x140007b05  add     rsp, 20h
0x140007b09  pop     rdi
0x140007b0a  retn
```
