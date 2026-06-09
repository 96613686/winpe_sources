# CWMIndexEntryArchiver::CleanUp(void)

- ea: `0x18000fe30`
- end: `0x18000ff19`
- name: `?CleanUp@CWMIndexEntryArchiver@@UEAAXXZ`
- size: `233`
- prototype: `void __fastcall(CWMIndexEntryArchiver *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x18000fdb8`

## callees

- `0x180001194`
- `0x180001f1c`
- `0x180007e38`
- `0x18000fe30`
- `0x180010268`

## import_xrefs

- `KERNEL32!DeleteFileW` at `0x18000fe64`
- `KERNEL32!DeleteFileW` at `0x18000fe64`
- `KERNEL32!CloseHandle` at `0x18000fe49`
- `KERNEL32!CloseHandle` at `0x18000fe49`

## pseudocode

```c
void __fastcall CWMIndexEntryArchiver::CleanUp(CWMIndexEntryArchiver *this)
{
  void *v2; // rcx
  unsigned __int64 v3; // rdx
  char *v4; // rsi
  char *v5; // rbx
  char *v6; // rcx

  v2 = (void *)*((_QWORD *)this + 1233);
  if ( v2 != (void *)-1LL )
  {
    CloseHandle(v2);
    *((_QWORD *)this + 1233) = -1;
  }
  DeleteFileW((LPCWSTR)this + 4936);
  *((_WORD *)this + 4936) = 0;
  *((_DWORD *)this + 2598) = 0;
  if ( *((_DWORD *)this + 2464) )
  {
    do
    {
      v4 = (char *)CTPtrArray<unsigned char,20>::operator[]((char *)this + 9640, 0);
      CTPtrArray<unsigned char,20>::RemoveAt((char *)this + 9640);
      v5 = (char *)this + 24;
      if ( v4 != (char *)this + 24 && v4 )
        operator delete(v4, v3);
    }
    while ( *((_DWORD *)this + 2464) );
  }
  else
  {
    v5 = (char *)this + 24;
  }
  v6 = (char *)*((_QWORD *)this + 1203);
  if ( v6 != v5 && v6 )
    operator delete(v6, v3);
  *((_QWORD *)this + 1203) = v5;
  *((_DWORD *)this + 5) = 0;
  *((_DWORD *)this + 2408) = 0;
  *((_DWORD *)this + 2599) = 0;
  *((_QWORD *)this + 1300) = 0;
  memset_0(v5, 0, 0x2580u);
}

```

## disassembly

```asm
0x18000fe30  push    rbx
0x18000fe32  push    rbp
0x18000fe33  push    rsi
0x18000fe34  push    rdi
0x18000fe35  sub     rsp, 28h
0x18000fe39  mov     rdi, rcx
0x18000fe3c  mov     rcx, [rcx+2688h]; hObject
0x18000fe43  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18000fe47  jz      short loc_18000FE5A
0x18000fe49  call    cs:__imp_CloseHandle
0x18000fe4f  mov     qword ptr [rdi+2688h], 0FFFFFFFFFFFFFFFFh
0x18000fe5a  lea     rbx, [rdi+2690h]
0x18000fe61  mov     rcx, rbx; lpFileName
0x18000fe64  call    cs:__imp_DeleteFileW
0x18000fe6a  xor     eax, eax
0x18000fe6c  mov     [rbx], ax
0x18000fe6f  mov     [rdi+2898h], eax
0x18000fe75  cmp     [rdi+2680h], eax
0x18000fe7b  jbe     short loc_18000FEBA
0x18000fe7d  lea     rbp, [rdi+25A8h]
0x18000fe84  xor     edx, edx
0x18000fe86  mov     rcx, rbp
0x18000fe89  call    ??A?$CTPtrArray@E$0BE@@@QEBAPEAEK@Z; CTPtrArray<uchar,20>::operator[](ulong)
0x18000fe8e  mov     rcx, rbp
0x18000fe91  mov     rsi, rax
0x18000fe94  call    ?RemoveAt@?$CTPtrArray@E$0BE@@@QEAAHKK@Z; CTPtrArray<uchar,20>::RemoveAt(ulong,ulong)
0x18000fe99  lea     rbx, [rdi+18h]
0x18000fe9d  cmp     rsi, rbx
0x18000fea0  jz      short loc_18000FEAF
0x18000fea2  test    rsi, rsi
0x18000fea5  jz      short loc_18000FEAF
0x18000fea7  mov     rcx, rsi; void *
0x18000feaa  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000feaf  cmp     dword ptr [rdi+2680h], 0
0x18000feb6  ja      short loc_18000FE84
0x18000feb8  jmp     short loc_18000FEBE
0x18000feba  lea     rbx, [rdi+18h]
0x18000febe  mov     rcx, [rdi+2598h]; void *
0x18000fec5  cmp     rcx, rbx
0x18000fec8  jz      short loc_18000FED4
0x18000feca  test    rcx, rcx
0x18000fecd  jz      short loc_18000FED4
0x18000fecf  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000fed4  xor     edx, edx; Val
0x18000fed6  mov     [rdi+2598h], rbx
0x18000fedd  mov     r8d, 2580h; Size
0x18000fee3  mov     dword ptr [rdi+14h], 0
0x18000feea  mov     rcx, rbx; void *
0x18000feed  mov     dword ptr [rdi+25A0h], 0
0x18000fef7  mov     dword ptr [rdi+289Ch], 0
0x18000ff01  mov     qword ptr [rdi+28A0h], 0
0x18000ff0c  add     rsp, 28h
0x18000ff10  pop     rdi
0x18000ff11  pop     rsi
0x18000ff12  pop     rbp
0x18000ff13  pop     rbx
0x18000ff14  jmp     memset_0
```
