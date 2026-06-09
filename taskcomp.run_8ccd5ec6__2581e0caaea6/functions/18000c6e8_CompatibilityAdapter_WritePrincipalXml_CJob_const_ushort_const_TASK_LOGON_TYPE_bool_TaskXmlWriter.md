# CompatibilityAdapter::WritePrincipalXml(CJob const *,ushort const *,_TASK_LOGON_TYPE,bool,TaskXmlWriter &)

- ea: `0x18000c6e8`
- end: `0x18000c801`
- name: `?WritePrincipalXml@CompatibilityAdapter@@AEAAJPEBVCJob@@PEBGW4_TASK_LOGON_TYPE@@_NAEAVTaskXmlWriter@@@Z`
- size: `281`
- prototype: `__int64 __fastcall(CompatibilityAdapter *__hidden this, const struct CJob *, const unsigned __int16 *, enum _TASK_LOGON_TYPE, bool, struct TaskXmlWriter *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000aa9c`

## callees

- `0x18000c6e8`
- `0x18001daa8`
- `0x18001dfe4`
- `0x18001e37c`
- `0x18001e4e0`

## string_xrefs

- `0x18000c6fd`: `InteractiveToken`
- `0x18000c708`: `InteractiveTokenOrPassword`
- `0x18000c77c`: `InteractiveTokenOrPassword`
- `0x18000c76c`: `@AtServiceAccount`

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
  const unsigned __int16 *v8; // rdi
  __int64 result; // rax
  int v10; // eax
  unsigned int v11; // ecx

  if ( a4 == TASK_LOGON_INTERACTIVE_TOKEN )
  {
    v8 = L"InteractiveToken";
  }
  else
  {
    v8 = L"InteractiveTokenOrPassword";
    if ( a4 != TASK_LOGON_INTERACTIVE_TOKEN_OR_PASSWORD )
      v8 = 0;
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
          result = TaskXmlWriter::Element(a6, 36, L"@AtServiceAccount");
          if ( (int)result < 0 )
            return result;
          result = TaskXmlWriter::Element(a6, 100, L"InteractiveTokenOrPassword");
          if ( (int)result < 0 )
            return result;
        }
        else
        {
          result = TaskXmlWriter::Element(a6, 36, a3);
          if ( (int)result < 0 )
            return result;
          if ( v8 )
          {
            result = TaskXmlWriter::Element(a6, 100, v8);
            if ( (int)result < 0 )
              return result;
          }
          if ( !a5 )
            goto LABEL_17;
        }
        result = TaskXmlWriter::Element(a6, 101, L"HighestAvailable");
        if ( (int)result < 0 )
          return result;
LABEL_17:
        result = TaskXmlWriter::EndElement(a6);
        if ( (int)result >= 0 )
        {
          v10 = TaskXmlWriter::EndElement(a6);
          v11 = 0;
          if ( v10 < 0 )
            return (unsigned int)v10;
          return v11;
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000c6e8  push    rbx
0x18000c6ea  push    rbp
0x18000c6eb  push    rsi
0x18000c6ec  push    rdi
0x18000c6ed  sub     rsp, 28h
0x18000c6f1  mov     rbp, r8
0x18000c6f4  mov     rsi, rdx
0x18000c6f7  cmp     r9d, 3
0x18000c6fb  jnz     short loc_18000C706
0x18000c6fd  lea     rdi, aInteractivetok; "InteractiveToken"
0x18000c704  jmp     short loc_18000C717
0x18000c706  xor     eax, eax
0x18000c708  lea     rdi, aInteractivetok_0; "InteractiveTokenOrPassword"
0x18000c70f  cmp     r9d, 6
0x18000c713  cmovnz  rdi, rax
0x18000c717  mov     rbx, [rsp+48h+arg_28]
0x18000c71c  mov     edx, 61h ; 'a'
0x18000c721  mov     rcx, rbx
0x18000c724  call    ?StartElement@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@@Z; TaskXmlWriter::StartElement(TaskXmlNodeId)
0x18000c729  test    eax, eax
0x18000c72b  js      loc_18000C7F7
0x18000c731  mov     edx, 62h ; 'b'
0x18000c736  mov     rcx, rbx
0x18000c739  call    ?StartElement@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@@Z; TaskXmlWriter::StartElement(TaskXmlNodeId)
0x18000c73e  test    eax, eax
0x18000c740  js      loc_18000C7F7
0x18000c746  mov     edx, 63h ; 'c'
0x18000c74b  mov     rcx, rbx
0x18000c74e  call    ?WriteAttribute@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@PEBG@Z; TaskXmlWriter::WriteAttribute(TaskXmlNodeId,ushort const *)
0x18000c753  test    eax, eax
0x18000c755  js      loc_18000C7F7
0x18000c75b  test    dword ptr [rsi+58h], 200000h
0x18000c762  mov     edx, 24h ; '$'
0x18000c767  mov     rcx, rbx
0x18000c76a  jz      short loc_18000C7AE
0x18000c76c  lea     r8, aAtserviceaccou_0; "@AtServiceAccount"
0x18000c773  call    ?Element@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@PEBG@Z; TaskXmlWriter::Element(TaskXmlNodeId,ushort const *)
0x18000c778  test    eax, eax
0x18000c77a  js      short loc_18000C7F7
0x18000c77c  lea     r8, aInteractivetok_0; "InteractiveTokenOrPassword"
0x18000c783  mov     edx, 64h ; 'd'
0x18000c788  mov     rcx, rbx
0x18000c78b  call    ?Element@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@PEBG@Z; TaskXmlWriter::Element(TaskXmlNodeId,ushort const *)
0x18000c790  test    eax, eax
0x18000c792  js      short loc_18000C7F7
0x18000c794  lea     r8, aHighestavailab; "HighestAvailable"
0x18000c79b  mov     edx, 65h ; 'e'
0x18000c7a0  mov     rcx, rbx
0x18000c7a3  call    ?Element@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@PEBG@Z; TaskXmlWriter::Element(TaskXmlNodeId,ushort const *)
0x18000c7a8  test    eax, eax
0x18000c7aa  jns     short loc_18000C7DA
0x18000c7ac  jmp     short loc_18000C7F7
0x18000c7ae  mov     r8, rbp
0x18000c7b1  call    ?Element@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@PEBG@Z; TaskXmlWriter::Element(TaskXmlNodeId,ushort const *)
0x18000c7b6  test    eax, eax
0x18000c7b8  js      short loc_18000C7F7
0x18000c7ba  test    rdi, rdi
0x18000c7bd  jz      short loc_18000C7D3
0x18000c7bf  mov     r8, rdi
0x18000c7c2  mov     edx, 64h ; 'd'
0x18000c7c7  mov     rcx, rbx
0x18000c7ca  call    ?Element@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@PEBG@Z; TaskXmlWriter::Element(TaskXmlNodeId,ushort const *)
0x18000c7cf  test    eax, eax
0x18000c7d1  js      short loc_18000C7F7
0x18000c7d3  cmp     [rsp+48h+arg_20], 0
0x18000c7d8  jnz     short loc_18000C794
0x18000c7da  mov     rcx, rbx
0x18000c7dd  call    ?EndElement@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@@Z; TaskXmlWriter::EndElement(TaskXmlNodeId)
0x18000c7e2  test    eax, eax
0x18000c7e4  js      short loc_18000C7F7
0x18000c7e6  mov     rcx, rbx
0x18000c7e9  call    ?EndElement@TaskXmlWriter@@QEAAJW4TaskXmlNodeId@@@Z; TaskXmlWriter::EndElement(TaskXmlNodeId)
0x18000c7ee  xor     ecx, ecx
0x18000c7f0  test    eax, eax
0x18000c7f2  cmovs   ecx, eax
0x18000c7f5  mov     eax, ecx
0x18000c7f7  add     rsp, 28h
0x18000c7fb  pop     rdi
0x18000c7fc  pop     rsi
0x18000c7fd  pop     rbp
0x18000c7fe  pop     rbx
0x18000c7ff  retn
```
