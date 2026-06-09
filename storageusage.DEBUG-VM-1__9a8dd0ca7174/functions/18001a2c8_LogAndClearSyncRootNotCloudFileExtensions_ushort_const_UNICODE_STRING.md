# LogAndClearSyncRootNotCloudFileExtensions(ushort const *,_UNICODE_STRING *)

- ea: `0x18001a2c8`
- end: `0x18001a35f`
- name: `?LogAndClearSyncRootNotCloudFileExtensions@@YAXPEBGPEAU_UNICODE_STRING@@@Z`
- size: `151`
- prototype: `void __fastcall(const unsigned __int16 *, struct _UNICODE_STRING *)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1800180a0`
- `0x18001d8b0`

## callees

- `0x1800010b0`
- `0x1800018bc`
- `0x180005c94`
- `0x18001a2c8`

## pseudocode

```c
void __fastcall LogAndClearSyncRootNotCloudFileExtensions(const unsigned __int16 *a1, struct _UNICODE_STRING *a2)
{
  int v3; // ecx
  __int64 v4; // r8
  int v5; // r9d
  __int64 v6; // [rsp+58h] [rbp+10h] BYREF
  struct _UNICODE_STRING *v7; // [rsp+60h] [rbp+18h] BYREF
  __int64 v8; // [rsp+68h] [rbp+20h] BYREF

  if ( a2->Length )
  {
    if ( (unsigned int)dword_180040010 > 5 )
    {
      if ( (unsigned __int8)tlgKeywordOn(&dword_180040010, 0x400000000000LL) )
      {
        v6 = 0x1000000;
        v7 = a2;
        v8 = v4;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapBuffer<_UNICODE_STRING>,_tlgWrapperByVal<8>>(
          v3,
          (unsigned int)&dword_180037CEC,
          v4,
          v5,
          (__int64)&v8,
          (__int64)&v7,
          (__int64)&v6);
      }
    }
    memset_0(a2->Buffer, 0, a2->MaximumLength);
    a2->Length = 0;
  }
}

```

## disassembly

```asm
0x18001a2c8  mov     [rsp+arg_0], rbx
0x18001a2cd  push    rdi
0x18001a2ce  sub     rsp, 40h
0x18001a2d2  xor     edi, edi
0x18001a2d4  mov     rbx, rdx
0x18001a2d7  mov     r8, rcx
0x18001a2da  cmp     [rdx], di
0x18001a2dd  jbe     short loc_18001A354
0x18001a2df  mov     eax, cs:dword_180040010
0x18001a2e5  cmp     eax, 5
0x18001a2e8  jbe     short loc_18001A341
0x18001a2ea  mov     rdx, 400000000000h
0x18001a2f4  lea     rcx, dword_180040010
0x18001a2fb  call    _tlgKeywordOn
0x18001a300  test    al, al
0x18001a302  jz      short loc_18001A341
0x18001a304  lea     rax, [rsp+48h+arg_8]
0x18001a309  mov     [rsp+48h+arg_8], 1000000h
0x18001a312  mov     [rsp+48h+var_18], rax
0x18001a317  lea     rdx, dword_180037CEC
0x18001a31e  lea     rax, [rsp+48h+arg_10]
0x18001a323  mov     [rsp+48h+arg_10], rbx
0x18001a328  mov     [rsp+48h+var_20], rax
0x18001a32d  lea     rax, [rsp+48h+arg_18]
0x18001a332  mov     [rsp+48h+var_28], rax
0x18001a337  mov     [rsp+48h+arg_18], r8
0x18001a33c  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapBuffer@U_UNICODE_STRING@@@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapBuffer@U_UNICODE_STRING@@@@AEBU?$_tlgWrapperByVal@$07@@@Z
0x18001a341  movzx   r8d, word ptr [rbx+2]; Size
0x18001a346  xor     edx, edx; Val
0x18001a348  mov     rcx, [rbx+8]; void *
0x18001a34c  call    memset_0
0x18001a351  mov     [rbx], di
0x18001a354  mov     rbx, [rsp+48h+arg_0]
0x18001a359  add     rsp, 40h
0x18001a35d  pop     rdi
0x18001a35e  retn
```
