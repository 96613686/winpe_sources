# WFDStartConnectorPairWithOOB

- ea: `0x18002cd00`
- end: `0x18002ceae`
- name: `WFDStartConnectorPairWithOOB`
- size: `430`
- prototype: `__int64 __usercall@<rax>(unsigned int@<ecx>, unsigned __int8 *@<rdx>, __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x1800278a0`
- `0x18002c704`
- `0x18002cd00`
- `0x180038938`
- `0x180038e00`
- `0x180038fa8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18002ce1a`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18002ce1a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ce2c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ce2c`
- `MobileNetworking!HtDereferenceHandleWithTag` at `0x18002ce95`
- `MobileNetworking!HtDereferenceHandleWithTag` at `0x18002ce95`
- `MobileNetworking!HtReferenceHandleWithTag` at `0x18002ce6a`
- `MobileNetworking!HtReferenceHandleWithTag` at `0x18002ce6a`

## pseudocode

```c
__int64 __fastcall WFDStartConnectorPairWithOOB(
        unsigned int a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        _QWORD *a5)
{
  _QWORD *v5; // rbx
  _QWORD *v10; // r14
  DWORD Context; // eax
  DWORD CanNewOOBSessionStart; // edi
  HANDLE Thread; // rax
  __int64 v14; // rdx
  LPVOID lpParameter; // [rsp+30h] [rbp-58h] BYREF
  __int64 v17; // [rsp+98h] [rbp+10h] BYREF

  v5 = 0;
  lpParameter = 0;
  LODWORD(v17) = 0;
  if ( a2 && a1 && a4 && (v10 = a5) != 0 )
  {
    Context = WFDOOBClientCreateContext((struct _WFD_OOB_SESSION_CONTEXT **)&lpParameter);
    v5 = lpParameter;
    CanNewOOBSessionStart = Context;
    if ( !Context )
    {
      CanNewOOBSessionStart = WFDParseOOBBlob(a1, a2, (struct _WFD_OOB_BLOB_DATA *)((char *)lpParameter + 520));
      if ( !CanNewOOBSessionStart )
      {
        *((_DWORD *)v5 + 24) = 1;
        v5[10] = a4;
        v5[11] = a3;
        *((_DWORD *)v5 + 128) = *((_DWORD *)v5 + 132);
        *((_WORD *)v5 + 258) = *((_WORD *)v5 + 266);
        CanNewOOBSessionStart = WFDOOBHelperCanNewOOBSessionStart(
                                  (struct _WFD_OOB_SESSION_CONTEXT *)v5,
                                  (enum _WFD_OOB_SESSION_ACTION *)&v17);
        if ( !CanNewOOBSessionStart )
        {
          *((_DWORD *)v5 + 233) = v17;
          if ( (unsigned int)wfdConnectorOobValidateListenerOobBlob((struct _WFD_OOB_BLOB_DATA *)(v5 + 65)) )
          {
            CanNewOOBSessionStart = WFDOobHelperSetPCDiscoverable(1, (struct _WFD_OOB_SESSION_CONTEXT *)v5);
            if ( !CanNewOOBSessionStart )
            {
              Thread = CreateThread(0, 0, wfdStartConnectorPairWithOobThreadProc, v5, 0, 0);
              v5[123] = Thread;
              if ( Thread )
              {
                v14 = *v5;
                v17 = 0;
                HtReferenceHandleWithTag(g_hHandleTable, v14, 269488144, 0, 1, &v17);
                *v10 = *v5;
                return CanNewOOBSessionStart;
              }
              CanNewOOBSessionStart = GetLastError();
            }
          }
          else
          {
            CanNewOOBSessionStart = 13;
          }
        }
      }
    }
  }
  else
  {
    CanNewOOBSessionStart = 87;
  }
  if ( v5 )
    HtDereferenceHandleWithTag(g_hHandleTable, *v5, 0, 1);
  return CanNewOOBSessionStart;
}

```

## disassembly

```asm
0x18002cd00  mov     rax, rsp
0x18002cd03  push    rbx
0x18002cd04  push    rbp
0x18002cd05  push    rsi
0x18002cd06  push    rdi
0x18002cd07  push    r12
0x18002cd09  push    r13
0x18002cd0b  push    r14
0x18002cd0d  push    r15
0x18002cd0f  sub     rsp, 48h
0x18002cd13  xor     ebx, ebx
0x18002cd15  mov     rbp, r9
0x18002cd18  mov     [rax-58h], rbx
0x18002cd1c  mov     r13, r8
0x18002cd1f  mov     [rax+10h], ebx
0x18002cd22  mov     r12, rdx
0x18002cd25  mov     esi, ecx
0x18002cd27  test    rdx, rdx
0x18002cd2a  jz      loc_18002CE78
0x18002cd30  test    ecx, ecx
0x18002cd32  jz      loc_18002CE78
0x18002cd38  test    r9, r9
0x18002cd3b  jz      loc_18002CE78
0x18002cd41  mov     r14, [rsp+88h+arg_20]
0x18002cd49  test    r14, r14
0x18002cd4c  jz      loc_18002CE78
0x18002cd52  lea     rcx, [rax-58h]; struct _WFD_OOB_SESSION_CONTEXT **
0x18002cd56  call    ?WFDOOBClientCreateContext@@YAKPEAPEAU_WFD_OOB_SESSION_CONTEXT@@@Z; WFDOOBClientCreateContext(_WFD_OOB_SESSION_CONTEXT * *)
0x18002cd5b  mov     rbx, [rsp+88h+lpParameter]
0x18002cd60  mov     edi, eax
0x18002cd62  test    eax, eax
0x18002cd64  jnz     loc_18002CE7D
0x18002cd6a  lea     r15, [rbx+208h]
0x18002cd71  mov     rdx, r12; unsigned __int8 *
0x18002cd74  mov     r8, r15; struct _WFD_OOB_BLOB_DATA *
0x18002cd77  mov     ecx, esi; unsigned int
0x18002cd79  call    WFDParseOOBBlob
0x18002cd7e  mov     edi, eax
0x18002cd80  test    eax, eax
0x18002cd82  jnz     loc_18002CE7D
0x18002cd88  mov     dword ptr [rbx+60h], 1
0x18002cd8f  lea     rdx, [rsp+88h+arg_8]; enum _WFD_OOB_SESSION_ACTION *
0x18002cd97  mov     [rbx+50h], rbp
0x18002cd9b  mov     rcx, rbx; struct _WFD_OOB_SESSION_CONTEXT *
0x18002cd9e  mov     [rbx+58h], r13
0x18002cda2  mov     eax, [rbx+210h]
0x18002cda8  mov     [rbx+200h], eax
0x18002cdae  movzx   eax, word ptr [rbx+214h]
0x18002cdb5  mov     [rbx+204h], ax
0x18002cdbc  call    ?WFDOOBHelperCanNewOOBSessionStart@@YAKPEAU_WFD_OOB_SESSION_CONTEXT@@PEAW4_WFD_OOB_SESSION_ACTION@@@Z; WFDOOBHelperCanNewOOBSessionStart(_WFD_OOB_SESSION_CONTEXT *,_WFD_OOB_SESSION_ACTION *)
0x18002cdc1  mov     edi, eax
0x18002cdc3  test    eax, eax
0x18002cdc5  jnz     loc_18002CE7D
0x18002cdcb  mov     eax, dword ptr [rsp+88h+arg_8]
0x18002cdd2  mov     rcx, r15; struct _WFD_OOB_BLOB_DATA *
0x18002cdd5  mov     [rbx+3A4h], eax
0x18002cddb  call    ?wfdConnectorOobValidateListenerOobBlob@@YAHPEAU_WFD_OOB_BLOB_DATA@@@Z; wfdConnectorOobValidateListenerOobBlob(_WFD_OOB_BLOB_DATA *)
0x18002cde0  test    eax, eax
0x18002cde2  jnz     short loc_18002CDEC
0x18002cde4  lea     edi, [rax+0Dh]
0x18002cde7  jmp     loc_18002CE7D
0x18002cdec  mov     rdx, rbx; struct _WFD_OOB_SESSION_CONTEXT *
0x18002cdef  mov     ecx, 1; int
0x18002cdf4  call    ?WFDOobHelperSetPCDiscoverable@@YAKHPEAU_WFD_OOB_SESSION_CONTEXT@@@Z; WFDOobHelperSetPCDiscoverable(int,_WFD_OOB_SESSION_CONTEXT *)
0x18002cdf9  mov     edi, eax
0x18002cdfb  test    eax, eax
0x18002cdfd  jnz     short loc_18002CE7D
0x18002cdff  mov     [rsp+88h+lpThreadId], 0; lpThreadId
0x18002ce08  lea     r8, ?wfdStartConnectorPairWithOobThreadProc@@YAKPEAX@Z; lpStartAddress
0x18002ce0f  mov     r9, rbx; lpParameter
0x18002ce12  mov     [rsp+88h+dwCreationFlags], eax; dwCreationFlags
0x18002ce16  xor     edx, edx; dwStackSize
0x18002ce18  xor     ecx, ecx; lpThreadAttributes
0x18002ce1a  call    cs:__imp_CreateThread
0x18002ce20  mov     [rbx+3D8h], rax
0x18002ce27  test    rax, rax
0x18002ce2a  jnz     short loc_18002CE36
0x18002ce2c  call    cs:__imp_GetLastError
0x18002ce32  mov     edi, eax
0x18002ce34  jmp     short loc_18002CE7D
0x18002ce36  mov     rdx, [rbx]
0x18002ce39  lea     rax, [rsp+88h+arg_8]
0x18002ce41  mov     rcx, cs:?g_hHandleTable@@3PEAXEA; void * g_hHandleTable
0x18002ce48  xor     r9d, r9d
0x18002ce4b  mov     [rsp+88h+lpThreadId], rax
0x18002ce50  mov     r8d, 10101010h
0x18002ce56  mov     [rsp+88h+dwCreationFlags], 1
0x18002ce5e  mov     [rsp+88h+arg_8], 0
0x18002ce6a  call    cs:__imp_HtReferenceHandleWithTag
0x18002ce70  mov     rax, [rbx]
0x18002ce73  mov     [r14], rax
0x18002ce76  jmp     short loc_18002CE9B
0x18002ce78  mov     edi, 57h ; 'W'
0x18002ce7d  test    rbx, rbx
0x18002ce80  jz      short loc_18002CE9B
0x18002ce82  mov     rdx, [rbx]
0x18002ce85  mov     r9d, 1
0x18002ce8b  mov     rcx, cs:?g_hHandleTable@@3PEAXEA; void * g_hHandleTable
0x18002ce92  xor     r8d, r8d
0x18002ce95  call    cs:__imp_HtDereferenceHandleWithTag
0x18002ce9b  mov     eax, edi
0x18002ce9d  add     rsp, 48h
0x18002cea1  pop     r15
0x18002cea3  pop     r14
0x18002cea5  pop     r13
0x18002cea7  pop     r12
0x18002cea9  pop     rdi
0x18002ceaa  pop     rsi
0x18002ceab  pop     rbp
0x18002ceac  pop     rbx
0x18002cead  retn
```
