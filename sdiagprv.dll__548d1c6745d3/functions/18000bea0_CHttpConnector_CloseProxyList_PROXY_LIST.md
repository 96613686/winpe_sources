# CHttpConnector::CloseProxyList(_PROXY_LIST *)

- ea: `0x18000bea0`
- end: `0x18000bf77`
- name: `?CloseProxyList@CHttpConnector@@AEAAJPEAU_PROXY_LIST@@@Z`
- size: `215`
- prototype: `__int64 __fastcall(CHttpConnector *__hidden this, struct _PROXY_LIST *)`
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000b6f4`
- `0x18000b9f0`
- `0x18000c618`
- `0x18000c980`

## callees

- `0x1800024d4`
- `0x18000bea0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000bed2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000bef7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000bf37`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000bed2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000bef7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000bf37`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000bec4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000bee9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000bf29`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000bec4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000bee9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000bf29`

## pseudocode

```c
__int64 __fastcall CHttpConnector::CloseProxyList(CHttpConnector *this, struct _PROXY_LIST *a2)
{
  void *v3; // rbx
  HANDLE ProcessHeap; // rax
  void *v5; // rbx
  HANDLE v6; // rax
  struct _PROXY_LIST *v7; // rsi
  __int64 v8; // rax
  struct _PROXY_LIST **v9; // rcx
  struct _PROXY_LIST *v10; // rbx
  HANDLE v11; // rax

  if ( a2 )
  {
    v3 = (void *)*((_QWORD *)a2 + 4);
    if ( v3 )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v3);
      *((_QWORD *)a2 + 4) = 0;
    }
    v5 = (void *)*((_QWORD *)a2 + 5);
    if ( v5 )
    {
      v6 = GetProcessHeap();
      HeapFree(v6, 0, v5);
      *((_QWORD *)a2 + 5) = 0;
    }
    v7 = *(struct _PROXY_LIST **)a2;
    while ( v7 != a2 )
    {
      v8 = *(_QWORD *)v7;
      if ( *(struct _PROXY_LIST **)(*(_QWORD *)v7 + 8LL) != v7
        || (v9 = (struct _PROXY_LIST **)*((_QWORD *)v7 + 1), *v9 != v7) )
      {
        __fastfail(3u);
      }
      *v9 = (struct _PROXY_LIST *)v8;
      v10 = v7;
      v7 = (struct _PROXY_LIST *)v8;
      *(_QWORD *)(v8 + 8) = v9;
      v11 = GetProcessHeap();
      HeapFree(v11, 0, v10);
    }
  }
  if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x100) != 0 )
    McTemplateU0s_EventWriteTransfer(this, SDIAGPRV_EVENT_DEBUG_SUCCESS, "CHttpConnector::CloseProxyList");
  return 0;
}

```

## disassembly

```asm
0x18000bea0  mov     [rsp+arg_0], rbx
0x18000bea5  mov     [rsp+arg_8], rsi
0x18000beaa  push    rdi
0x18000beab  sub     rsp, 20h
0x18000beaf  mov     rdi, rdx
0x18000beb2  test    rdx, rdx
0x18000beb5  jz      loc_18000BF42
0x18000bebb  mov     rbx, [rdx+20h]
0x18000bebf  test    rbx, rbx
0x18000bec2  jz      short loc_18000BEE0
0x18000bec4  call    cs:__imp_GetProcessHeap
0x18000beca  mov     r8, rbx; lpMem
0x18000becd  xor     edx, edx; dwFlags
0x18000becf  mov     rcx, rax; hHeap
0x18000bed2  call    cs:__imp_HeapFree
0x18000bed8  mov     qword ptr [rdi+20h], 0
0x18000bee0  mov     rbx, [rdi+28h]
0x18000bee4  test    rbx, rbx
0x18000bee7  jz      short loc_18000BF05
0x18000bee9  call    cs:__imp_GetProcessHeap
0x18000beef  mov     r8, rbx; lpMem
0x18000bef2  xor     edx, edx; dwFlags
0x18000bef4  mov     rcx, rax; hHeap
0x18000bef7  call    cs:__imp_HeapFree
0x18000befd  mov     qword ptr [rdi+28h], 0
0x18000bf05  mov     rsi, [rdi]
0x18000bf08  jmp     short loc_18000BF3D
0x18000bf0a  mov     rax, [rsi]
0x18000bf0d  cmp     [rax+8], rsi
0x18000bf11  jnz     short loc_18000BF70
0x18000bf13  mov     rcx, [rsi+8]
0x18000bf17  cmp     [rcx], rsi
0x18000bf1a  jnz     short loc_18000BF70
0x18000bf1c  mov     [rcx], rax
0x18000bf1f  mov     rbx, rsi
0x18000bf22  mov     rsi, rax
0x18000bf25  mov     [rax+8], rcx
0x18000bf29  call    cs:__imp_GetProcessHeap
0x18000bf2f  mov     r8, rbx; lpMem
0x18000bf32  xor     edx, edx; dwFlags
0x18000bf34  mov     rcx, rax; hHeap
0x18000bf37  call    cs:__imp_HeapFree
0x18000bf3d  cmp     rsi, rdi
0x18000bf40  jnz     short loc_18000BF0A
0x18000bf42  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 1
0x18000bf49  jz      short loc_18000BF5E
0x18000bf4b  lea     r8, aChttpconnector_15; "CHttpConnector::CloseProxyList"
0x18000bf52  lea     rdx, SDIAGPRV_EVENT_DEBUG_SUCCESS
0x18000bf59  call    McTemplateU0s_EventWriteTransfer
0x18000bf5e  mov     rbx, [rsp+28h+arg_0]
0x18000bf63  xor     eax, eax
0x18000bf65  mov     rsi, [rsp+28h+arg_8]
0x18000bf6a  add     rsp, 20h
0x18000bf6e  pop     rdi
0x18000bf6f  retn
0x18000bf70  mov     ecx, 3
0x18000bf75  int     29h; Win8: RtlFailFast(ecx)
```
