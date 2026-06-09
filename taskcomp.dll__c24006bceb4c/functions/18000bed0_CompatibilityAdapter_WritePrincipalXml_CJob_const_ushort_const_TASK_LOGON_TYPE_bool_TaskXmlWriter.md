# CompatibilityAdapter::WritePrincipalXml(CJob const *,ushort const *,_TASK_LOGON_TYPE,bool,TaskXmlWriter &)

- ea: `0x18000bed0`
- end: `0x18000bfe8`
- name: `?WritePrincipalXml@CompatibilityAdapter@@AEAAJPEBVCJob@@PEBGW4_TASK_LOGON_TYPE@@_NAEAVTaskXmlWriter@@@Z`
- size: `280`
- prototype: `__int64 __fastcall(CompatibilityAdapter *__hidden this, const struct CJob *, const unsigned __int16 *, enum _TASK_LOGON_TYPE, bool, struct TaskXmlWriter *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000a4b4`

## callees

- `0x18000bed0`
- `0x18001c558`
- `0x18001ca88`
- `0x18001ce0c`
- `0x18001cf70`

## string_xrefs

- `0x18000bee5`: `InteractiveToken`
- `0x18000bef0`: `InteractiveTokenOrPassword`
- `0x18000bf64`: `InteractiveTokenOrPassword`
- `0x18000bf54`: `@AtServiceAccount`

## pseudocode

```c
__int64 __fastcall CompatibilityAdapter::WritePrincipalXml(
        CompatibilityAdapter *this,
        const struct CJob *a2,
        const unsigned __int16 *a3,
        enum _TASK_LOGON_TYPE a4,
        bool a5,
        struct TaskXmlWriter *a6)
{
  const unsigned __int16 *v7; // rdi
  __int64 result; // rax
  int v9; // eax
  unsigned int v10; // ecx

  if ( a4 == TASK_LOGON_INTERACTIVE_TOKEN )
  {
    v7 = L"InteractiveToken";
  }
  else
  {
    v7 = L"InteractiveTokenOrPassword";
    if ( a4 != TASK_LOGON_INTERACTIVE_TOKEN_OR_PASSWORD )
      v7 = 0;
  }
  result = TaskXmlWriter::StartElement(a6, 97);
  if ( (int)result >= 0 )
  {
    result = TaskXmlWriter::StartElement(a6, 98);
    if ( (int)result >= 0 )
    {
      result = TaskXmlWriter::WriteAttribute(a6, 99);
      if ( (int)result >= 0 )
      {
        if ( (*((_DWORD *)a2 + 22) & 0x200000) != 0 )
        {
          result = TaskXmlWriter::Element(a6, 36);
          if ( (int)result < 0 )
            return result;
          result = TaskXmlWriter::Element(a6, 100);
          if ( (int)result < 0 )
            return result;
        }
        else
        {
          result = TaskXmlWriter::Element(a6, 36);
          if ( (int)result < 0 )
            return result;
          if ( v7 )
          {
            result = TaskXmlWriter::Element(a6, 100);
            if ( (int)result < 0 )
              return result;
          }
          if ( !a5 )
            goto LABEL_17;
        }
        result = TaskXmlWriter::Element(a6, 101);
        if ( (int)result < 0 )
          return result;
LABEL_17:
        result = TaskXmlWriter::EndElement(a6);
        if ( (int)result >= 0 )
        {
          v9 = TaskXmlWriter::EndElement(a6);
          v10 = 0;
          if ( v9 < 0 )
            return (unsigned int)v9;
          return v10;
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000bed0  push    rbx
0x18000bed2  push    rbp
0x18000bed3  push    rsi
0x18000bed4  push    rdi
0x18000bed5  sub     rsp, 28h
0x18000bed9  mov     rbp, r8
0x18000bedc  mov     rsi, rdx
0x18000bedf  cmp     r9d, 3
0x18000bee3  jnz     short loc_18000BEEE
0x18000bee5  lea     rdi, aInteractivetok; "InteractiveToken"
0x18000beec  jmp     short loc_18000BEFF
0x18000beee  xor     eax, eax
0x18000bef0  lea     rdi, aInteractivetok_0; "InteractiveTokenOrPassword"
0x18000bef7  cmp     r9d, 6
0x18000befb  cmovnz  rdi, rax
0x18000beff  mov     rbx, [rsp+48h+arg_28]
0x18000bf04  mov     edx, 61h ; 'a'
0x18000bf09  mov     rcx, rbx
0x18000bf0c  call    ?StartElement@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@@Z; TaskXmlWriter::StartElement(TaskXmlNodeId)
0x18000bf11  test    eax, eax
0x18000bf13  js      loc_18000BFDF
0x18000bf19  mov     edx, 62h ; 'b'
0x18000bf1e  mov     rcx, rbx
0x18000bf21  call    ?StartElement@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@@Z; TaskXmlWriter::StartElement(TaskXmlNodeId)
0x18000bf26  test    eax, eax
0x18000bf28  js      loc_18000BFDF
0x18000bf2e  mov     edx, 63h ; 'c'
0x18000bf33  mov     rcx, rbx
0x18000bf36  call    ?WriteAttribute@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@PEBG@Z; TaskXmlWriter::WriteAttribute(TaskXmlNodeId,ushort const *)
0x18000bf3b  test    eax, eax
0x18000bf3d  js      loc_18000BFDF
0x18000bf43  test    dword ptr [rsi+58h], 200000h
0x18000bf4a  mov     edx, 24h ; '$'
0x18000bf4f  mov     rcx, rbx
0x18000bf52  jz      short loc_18000BF96
0x18000bf54  lea     r8, aAtserviceaccou_0; "@AtServiceAccount"
0x18000bf5b  call    ?Element@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@PEBG@Z; TaskXmlWriter::Element(TaskXmlNodeId,ushort const *)
0x18000bf60  test    eax, eax
0x18000bf62  js      short loc_18000BFDF
0x18000bf64  lea     r8, aInteractivetok_0; "InteractiveTokenOrPassword"
0x18000bf6b  mov     edx, 64h ; 'd'
0x18000bf70  mov     rcx, rbx
0x18000bf73  call    ?Element@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@PEBG@Z; TaskXmlWriter::Element(TaskXmlNodeId,ushort const *)
0x18000bf78  test    eax, eax
0x18000bf7a  js      short loc_18000BFDF
0x18000bf7c  lea     r8, aHighestavailab; "HighestAvailable"
0x18000bf83  mov     edx, 65h ; 'e'
0x18000bf88  mov     rcx, rbx
0x18000bf8b  call    ?Element@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@PEBG@Z; TaskXmlWriter::Element(TaskXmlNodeId,ushort const *)
0x18000bf90  test    eax, eax
0x18000bf92  jns     short loc_18000BFC2
0x18000bf94  jmp     short loc_18000BFDF
0x18000bf96  mov     r8, rbp
0x18000bf99  call    ?Element@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@PEBG@Z; TaskXmlWriter::Element(TaskXmlNodeId,ushort const *)
0x18000bf9e  test    eax, eax
0x18000bfa0  js      short loc_18000BFDF
0x18000bfa2  test    rdi, rdi
0x18000bfa5  jz      short loc_18000BFBB
0x18000bfa7  mov     r8, rdi
0x18000bfaa  mov     edx, 64h ; 'd'
0x18000bfaf  mov     rcx, rbx
0x18000bfb2  call    ?Element@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@PEBG@Z; TaskXmlWriter::Element(TaskXmlNodeId,ushort const *)
0x18000bfb7  test    eax, eax
0x18000bfb9  js      short loc_18000BFDF
0x18000bfbb  cmp     [rsp+48h+arg_20], 0
0x18000bfc0  jnz     short loc_18000BF7C
0x18000bfc2  mov     rcx, rbx
0x18000bfc5  call    ?EndElement@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@@Z; TaskXmlWriter::EndElement(TaskXmlNodeId)
0x18000bfca  test    eax, eax
0x18000bfcc  js      short loc_18000BFDF
0x18000bfce  mov     rcx, rbx
0x18000bfd1  call    ?EndElement@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@@Z; TaskXmlWriter::EndElement(TaskXmlNodeId)
0x18000bfd6  xor     ecx, ecx
0x18000bfd8  test    eax, eax
0x18000bfda  cmovs   ecx, eax
0x18000bfdd  mov     eax, ecx
0x18000bfdf  add     rsp, 28h
0x18000bfe3  pop     rdi
0x18000bfe4  pop     rsi
0x18000bfe5  pop     rbp
0x18000bfe6  pop     rbx
0x18000bfe7  retn
```
