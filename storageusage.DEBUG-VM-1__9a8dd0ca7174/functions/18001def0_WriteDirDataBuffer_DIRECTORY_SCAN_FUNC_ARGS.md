# WriteDirDataBuffer(DIRECTORY_SCAN_FUNC_ARGS *)

- ea: `0x18001def0`
- end: `0x18001dfbd`
- name: `?WriteDirDataBuffer@@YAXPEAUDIRECTORY_SCAN_FUNC_ARGS@@@Z`
- size: `205`
- prototype: `void __fastcall(struct DIRECTORY_SCAN_FUNC_ARGS *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18001aec0`

## callees

- `0x1800010b0`
- `0x180002318`
- `0x180005c94`
- `0x18001def0`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18001df83`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18001df83`

## pseudocode

```c
void __fastcall WriteDirDataBuffer(struct DIRECTORY_SCAN_FUNC_ARGS *a1)
{
  int v2; // ecx
  int v3; // r8d
  int v4; // r9d
  void *v5; // rcx
  __int64 v6; // [rsp+40h] [rbp-18h] BYREF
  __int16 v7; // [rsp+48h] [rbp-10h]
  char *v8; // [rsp+60h] [rbp+8h] BYREF
  __int64 v9; // [rsp+68h] [rbp+10h] BYREF

  if ( *((_WORD *)a1 + 44) )
  {
    if ( (unsigned int)dword_180040010 > 5 )
    {
      if ( (unsigned __int8)tlgKeywordOn(&dword_180040010, 0x400000000000LL) )
      {
        v7 = v3;
        v8 = (char *)a1 + 96;
        v6 = *((_QWORD *)a1 + 14);
        v9 = 0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperArray<8>,_tlgWrapBuffer<_UNICODE_STRING>>(
          v2,
          (unsigned int)&byte_180037797,
          v3,
          v4,
          (__int64)&v9,
          (__int64)&v6,
          (__int64)&v8);
      }
    }
    Sleep(0x28u);
    v5 = (void *)*((_QWORD *)a1 + 14);
    *((_WORD *)a1 + 44) = 0;
    *((_WORD *)a1 + 48) = 0;
    memset_0(v5, 0, 0x1F40u);
    memset_0(*((void **)a1 + 13), 0, *((unsigned __int16 *)a1 + 49));
  }
}

```

## disassembly

```asm
0x18001def0  mov     [rsp+arg_10], rbx
0x18001def5  push    rdi
0x18001def6  sub     rsp, 50h
0x18001defa  movzx   r8d, word ptr [rcx+58h]
0x18001deff  xor     edi, edi
0x18001df01  mov     rbx, rcx
0x18001df04  test    r8w, r8w
0x18001df08  jz      loc_18001DFB2
0x18001df0e  mov     eax, cs:dword_180040010
0x18001df14  cmp     eax, 5
0x18001df17  jbe     short loc_18001DF7E
0x18001df19  mov     rdx, 400000000000h
0x18001df23  lea     rcx, dword_180040010
0x18001df2a  call    _tlgKeywordOn
0x18001df2f  test    al, al
0x18001df31  jz      short loc_18001DF7E
0x18001df33  lea     rax, [rbx+60h]
0x18001df37  mov     [rsp+58h+var_10], r8w
0x18001df3d  mov     [rsp+58h+arg_0], rax
0x18001df42  lea     rdx, byte_180037797
0x18001df49  mov     rax, [rbx+70h]
0x18001df4d  mov     [rsp+58h+var_18], rax
0x18001df52  lea     rax, [rsp+58h+arg_0]
0x18001df57  mov     [rsp+58h+var_28], rax
0x18001df5c  lea     rax, [rsp+58h+var_18]
0x18001df61  mov     [rsp+58h+var_30], rax
0x18001df66  lea     rax, [rsp+58h+arg_8]
0x18001df6b  mov     [rsp+58h+var_38], rax
0x18001df70  mov     [rsp+58h+arg_8], 1000000h
0x18001df79  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperArray@$07@@U?$_tlgWrapBuffer@U_UNICODE_STRING@@@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperArray@$07@@AEBU?$_tlgWrapBuffer@U_UNICODE_STRING@@@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperArray<8>,_tlgWrapBuffer<_UNICODE_STRING>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperArray<8> const &,_tlgWrapBuffer<_UNICODE_STRING> const &)
0x18001df7e  mov     ecx, 28h ; '('; dwMilliseconds
0x18001df83  call    cs:__imp_Sleep
0x18001df89  mov     rcx, [rbx+70h]; void *
0x18001df8d  xor     edx, edx; Val
0x18001df8f  mov     r8d, 1F40h; Size
0x18001df95  mov     [rbx+58h], di
0x18001df99  mov     [rbx+60h], di
0x18001df9d  call    memset_0
0x18001dfa2  movzx   r8d, word ptr [rbx+62h]; Size
0x18001dfa7  xor     edx, edx; Val
0x18001dfa9  mov     rcx, [rbx+68h]; void *
0x18001dfad  call    memset_0
0x18001dfb2  mov     rbx, [rsp+58h+arg_10]
0x18001dfb7  add     rsp, 50h
0x18001dfbb  pop     rdi
0x18001dfbc  retn
```
