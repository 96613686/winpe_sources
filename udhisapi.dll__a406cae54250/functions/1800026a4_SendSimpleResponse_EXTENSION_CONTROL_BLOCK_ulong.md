# SendSimpleResponse(_EXTENSION_CONTROL_BLOCK *,ulong)

- ea: `0x1800026a4`
- end: `0x18000287b`
- name: `?SendSimpleResponse@@YAXPEAU_EXTENSION_CONTROL_BLOCK@@K@Z`
- size: `471`
- prototype: `void __fastcall(struct _EXTENSION_CONTROL_BLOCK *, DWORD)`
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x180002110`
- `0x180003aa0`
- `0x180006e40`
- `0x180007734`

## callees

- `0x1800026a4`
- `0x180002884`

## string_xrefs

- `0x18000274d`: `201 Created`
- `0x180002765`: `301 Moved Permanently`
- `0x1800027b1`: `302 Moved Temporarily`
- `0x1800027fa`: `503 Service Unavailable`

## pseudocode

```c
void __fastcall SendSimpleResponse(struct _EXTENSION_CONTROL_BLOCK *a1, DWORD a2)
{
  const char *v2; // rax
  __int64 v4; // r8
  const char *v6; // rdx
  __int64 v7; // r8

  v2 = "\r\n";
  v4 = 0x7FFFFFFF;
  v6 = 0;
  do
  {
    if ( !*v2 )
      break;
    ++v2;
    --v4;
  }
  while ( v4 );
  v7 = (0x7FFFFFFF - v4) & -(__int64)(v4 != 0);
  if ( a2 > 0x193 )
  {
    switch ( a2 )
    {
      case 0x194u:
        v6 = "404 Not Found";
        break;
      case 0x195u:
        v6 = "405 Method Not Allowed";
        break;
      case 0x19Bu:
        v6 = "411 The Server Refused to Accept Request Without a Length";
        break;
      case 0x19Cu:
        v6 = "412 Precondition Failed";
        break;
      case 0x19Fu:
        v6 = "415 Unsupported Media Type";
        break;
      case 0x1F4u:
        v6 = "500 Internal Server Error";
        break;
      case 0x1F5u:
        v6 = "501 Not Implemented";
        break;
      case 0x1F6u:
        v6 = "502 Bad Gateway";
        break;
      case 0x1F7u:
        v6 = "503 Service Unavailable";
        break;
    }
  }
  else if ( a2 == 403 )
  {
    v6 = "403 Forbidden";
  }
  else if ( a2 > 0x12D )
  {
    switch ( a2 )
    {
      case 0x12Eu:
        v6 = "302 Moved Temporarily";
        break;
      case 0x130u:
        v6 = "304 Not Modified";
        break;
      case 0x190u:
        v6 = "400 Bad Request";
        break;
      case 0x191u:
        v6 = "401 Unauthorized";
        break;
    }
  }
  else
  {
    switch ( a2 )
    {
      case 0x12Du:
        v6 = "301 Moved Permanently";
        break;
      case 0xC8u:
        v6 = "200 OK";
        break;
      case 0xC9u:
        v6 = "201 Created";
        break;
      case 0xCAu:
        v6 = "202 Accepted";
        break;
      case 0xCCu:
        v6 = "204 No Content";
        break;
      case 0x12Cu:
        v6 = "300 Multiple";
        break;
    }
  }
  if ( (unsigned int)bSendResponseToClient(a1, v6, v7, "\r\n", 0, 0) )
    a1->dwHttpStatusCode = a2;
}

```

## disassembly

```asm
0x1800026a4  mov     [rsp+arg_0], rbx
0x1800026a9  push    rdi
0x1800026aa  sub     rsp, 30h
0x1800026ae  mov     r9d, 7FFFFFFFh
0x1800026b4  lea     rax, asc_18000D820; "\r\n"
0x1800026bb  mov     ebx, edx
0x1800026bd  mov     r8d, r9d
0x1800026c0  mov     rdi, rcx
0x1800026c3  xor     edx, edx
0x1800026c5  cmp     [rax], dl
0x1800026c7  jz      short loc_1800026D2
0x1800026c9  inc     rax
0x1800026cc  sub     r8, 1
0x1800026d0  jnz     short loc_1800026C5
0x1800026d2  sub     r9, r8
0x1800026d5  mov     rax, r8
0x1800026d8  neg     rax
0x1800026db  mov     eax, 193h
0x1800026e0  sbb     rcx, rcx
0x1800026e3  and     rcx, r9
0x1800026e6  neg     r8
0x1800026e9  sbb     r8, r8
0x1800026ec  and     r8, rcx; unsigned int
0x1800026ef  cmp     ebx, eax
0x1800026f1  ja      loc_1800027C9
0x1800026f7  jz      loc_1800027BD
0x1800026fd  mov     eax, 12Dh
0x180002702  cmp     ebx, eax
0x180002704  ja      short loc_180002771
0x180002706  jz      short loc_180002765
0x180002708  mov     eax, ebx
0x18000270a  sub     eax, 0C8h
0x18000270f  jz      short loc_180002759
0x180002711  sub     eax, 1
0x180002714  jz      short loc_18000274D
0x180002716  sub     eax, 1
0x180002719  jz      short loc_180002741
0x18000271b  sub     eax, 2
0x18000271e  jz      short loc_180002735
0x180002720  cmp     eax, 60h ; '`'
0x180002723  jnz     loc_180002849
0x180002729  lea     rdx, a300Multiple; "300 Multiple"
0x180002730  jmp     loc_180002849
0x180002735  lea     rdx, a204NoContent; "204 No Content"
0x18000273c  jmp     loc_180002849
0x180002741  lea     rdx, a202Accepted; "202 Accepted"
0x180002748  jmp     loc_180002849
0x18000274d  lea     rdx, a201Created; "201 Created"
0x180002754  jmp     loc_180002849
0x180002759  lea     rdx, a200Ok; "200 OK"
0x180002760  jmp     loc_180002849
0x180002765  lea     rdx, a301MovedPerman; "301 Moved Permanently"
0x18000276c  jmp     loc_180002849
0x180002771  mov     eax, ebx
0x180002773  sub     eax, 12Eh
0x180002778  jz      short loc_1800027B1
0x18000277a  sub     eax, 2
0x18000277d  jz      short loc_1800027A5
0x18000277f  sub     eax, 60h ; '`'
0x180002782  jz      short loc_180002799
0x180002784  cmp     eax, 1
0x180002787  jnz     loc_180002849
0x18000278d  lea     rdx, a401Unauthorize; "401 Unauthorized"
0x180002794  jmp     loc_180002849
0x180002799  lea     rdx, a400BadRequest; "400 Bad Request"
0x1800027a0  jmp     loc_180002849
0x1800027a5  lea     rdx, a304NotModified; "304 Not Modified"
0x1800027ac  jmp     loc_180002849
0x1800027b1  lea     rdx, a302MovedTempor; "302 Moved Temporarily"
0x1800027b8  jmp     loc_180002849
0x1800027bd  lea     rdx, a403Forbidden; "403 Forbidden"
0x1800027c4  jmp     loc_180002849
0x1800027c9  mov     eax, ebx
0x1800027cb  sub     eax, 194h
0x1800027d0  jz      short loc_180002842
0x1800027d2  sub     eax, 1
0x1800027d5  jz      short loc_180002839
0x1800027d7  sub     eax, 6
0x1800027da  jz      short loc_180002830
0x1800027dc  sub     eax, 1
0x1800027df  jz      short loc_180002827
0x1800027e1  sub     eax, 3
0x1800027e4  jz      short loc_18000281E
0x1800027e6  sub     eax, 55h ; 'U'
0x1800027e9  jz      short loc_180002815
0x1800027eb  sub     eax, 1
0x1800027ee  jz      short loc_18000280C
0x1800027f0  sub     eax, 1
0x1800027f3  jz      short loc_180002803
0x1800027f5  cmp     eax, 1
0x1800027f8  jnz     short loc_180002849
0x1800027fa  lea     rdx, a503ServiceUnav; "503 Service Unavailable"
0x180002801  jmp     short loc_180002849
0x180002803  lea     rdx, a502BadGateway; "502 Bad Gateway"
0x18000280a  jmp     short loc_180002849
0x18000280c  lea     rdx, a501NotImplemen; "501 Not Implemented"
0x180002813  jmp     short loc_180002849
0x180002815  lea     rdx, a500InternalSer; "500 Internal Server Error"
0x18000281c  jmp     short loc_180002849
0x18000281e  lea     rdx, a415Unsupported; "415 Unsupported Media Type"
0x180002825  jmp     short loc_180002849
0x180002827  lea     rdx, a412Preconditio; "412 Precondition Failed"
0x18000282e  jmp     short loc_180002849
0x180002830  lea     rdx, a411TheServerRe; "411 The Server Refused to Accept Reques"...
0x180002837  jmp     short loc_180002849
0x180002839  lea     rdx, a405MethodNotAl; "405 Method Not Allowed"
0x180002840  jmp     short loc_180002849
0x180002842  lea     rdx, a404NotFound; "404 Not Found"
0x180002849  mov     [rsp+38h+var_10], 0; char *
0x180002852  lea     r9, asc_18000D820; "\r\n"
0x180002859  mov     rcx, rdi; struct _EXTENSION_CONTROL_BLOCK *
0x18000285c  mov     [rsp+38h+var_18], 0; unsigned int
0x180002864  call    ?bSendResponseToClient@@YAHPEAU_EXTENSION_CONTROL_BLOCK@@PEBDK1K1@Z; bSendResponseToClient(_EXTENSION_CONTROL_BLOCK *,char const *,ulong,char const *,ulong,char const *)
0x180002869  test    eax, eax
0x18000286b  jz      short loc_180002870
0x18000286d  mov     [rdi+10h], ebx
0x180002870  mov     rbx, [rsp+38h+arg_0]
0x180002875  add     rsp, 30h
0x180002879  pop     rdi
0x18000287a  retn
```
